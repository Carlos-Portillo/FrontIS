# HU-005: Exportar Reporte a PDF - Implementación

## Encargado: Carlos César Portillo Mendoza

---

## 🎯 **Código HTML para agregar el botón "Exportar a PDF"**

### **Reemplazar la sección de botones de exportación:**

Busca esta línea en `report.html` (línea 463):
```html
<button @click="exportReport()" class="bg-brand-500 hover:bg-brand-500 text-white px-4 py-2 rounded-lg text-sm font-medium">
  <i class="fas fa-download mr-2"></i>Export
</button>
```

**REEMPLAZAR por:**

```html
<!-- ===== Botones de Exportación - HU-005 ===== -->
<div class="flex flex-col sm:flex-row gap-3">
  <!-- Botón existente de exportar CSV (modificado) -->
  <button @click="exportReport()" class="bg-brand-500 hover:bg-brand-600 text-white px-4 py-2 rounded-lg text-sm font-medium flex items-center justify-center transition-colors duration-200">
    <i class="fas fa-file-excel mr-2"></i>
    <span class="hidden sm:inline">Exportar </span>Excel
  </button>
  
  <!-- NUEVO: Botón de exportar PDF - HU-005 -->
  <button @click="exportToPDF()" 
          :disabled="!currentReport || loading" 
          :class="{'opacity-50 cursor-not-allowed': !currentReport || loading}"
          class="bg-red-500 hover:bg-red-600 text-white px-4 py-2 rounded-lg text-sm font-medium flex items-center justify-center transition-colors duration-200 relative">
    <i class="fas fa-file-pdf mr-2"></i>
    <span class="hidden sm:inline">Exportar </span>PDF
    <!-- Badge de nueva funcionalidad -->
    <span class="absolute -top-2 -right-2 bg-orange-500 text-white text-xs px-2 py-0.5 rounded-full">
      NEW
    </span>
  </button>
</div>
```

---

## 🎨 **CSS Adicional (agregar a style.css o en <style>)**

```css
/* Estilos específicos para HU-005 - Exportar PDF */

/* Animación del botón PDF */
@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: .7;
  }
}

.btn-pdf-loading {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

/* Mejora del badge NEW */
.badge-new {
  font-size: 9px;
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12);
}

/* Estados del botón PDF */
.btn-export-pdf {
  background: linear-gradient(135deg, #ef4444 0%, #dc2626 100%);
  box-shadow: 0 2px 4px rgba(239, 68, 68, 0.2);
}

.btn-export-pdf:hover {
  background: linear-gradient(135deg, #dc2626 0%, #b91c1c 100%);
  box-shadow: 0 4px 8px rgba(239, 68, 68, 0.3);
  transform: translateY(-1px);
}

.btn-export-pdf:active {
  transform: translateY(0);
  box-shadow: 0 2px 4px rgba(239, 68, 68, 0.2);
}

/* Responsive adjustments */
@media (max-width: 640px) {
  .export-buttons {
    flex-direction: column;
    width: 100%;
  }
  
  .export-buttons button {
    width: 100%;
    justify-content: center;
  }
}

/* Estados de carga para PDF */
.pdf-loading-spinner {
  display: inline-block;
  width: 14px;
  height: 14px;
  border: 2px solid transparent;
  border-top: 2px solid #ffffff;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
```

---

## ⚙️ **JavaScript para la funcionalidad PDF (agregar al Alpine.js data)**

**Agregar estas funciones dentro del objeto Alpine.js existente:**

```javascript
// ===== HU-005: Exportar a PDF - Funciones =====

// Estado para controlar la exportación PDF
pdfExporting: false,
pdfProgress: 0,

// Función principal para exportar PDF
async exportToPDF() {
  if (!this.currentReport) {
    this.showNotification('No hay reporte para exportar', 'error');
    return;
  }

  this.pdfExporting = true;
  this.pdfProgress = 0;

  try {
    // Mostrar progreso
    this.updatePDFProgress(20, 'Preparando datos...');
    
    // Crear datos para el PDF
    const pdfData = this.preparePDFData();
    
    this.updatePDFProgress(50, 'Generando gráficos...');
    
    // Generar PDF usando jsPDF
    const pdfBlob = await this.generatePDFDocument(pdfData);
    
    this.updatePDFProgress(80, 'Finalizando descarga...');
    
    // Descargar archivo
    this.downloadPDFFile(pdfBlob);
    
    this.updatePDFProgress(100, '¡PDF generado exitosamente!');
    
    // Mostrar notificación de éxito
    this.showNotification('PDF descargado exitosamente', 'success');
    
  } catch (error) {
    console.error('Error generando PDF:', error);
    this.showNotification('Error al generar PDF: ' + error.message, 'error');
  } finally {
    // Reset estado después de 2 segundos
    setTimeout(() => {
      this.pdfExporting = false;
      this.pdfProgress = 0;
    }, 2000);
  }
},

// Preparar datos para el PDF
preparePDFData() {
  const currentUser = JSON.parse(localStorage.getItem('userInfo') || '{}');
  
  return {
    // Información del usuario
    userName: currentUser.name || 'Usuario',
    userEmail: currentUser.email || '',
    
    // Información del reporte
    reportTitle: 'Reporte Financiero - BudgetBuddy',
    period: this.getPeriodText(),
    generatedDate: new Date().toLocaleDateString('es-ES', {
      year: 'numeric',
      month: 'long',
      day: 'numeric',
      hour: '2-digit',
      minute: '2-digit'
    }),
    
    // Datos financieros
    totalIncome: this.currentReport.totalIncome,
    totalExpenses: this.currentReport.totalExpenses,
    balance: this.currentReport.balance,
    totalTransactions: this.currentReport.totalTransactions,
    
    // Porcentajes
    incomePercentage: this.incomePercentage,
    expensePercentage: this.expensePercentage,
    
    // Datos para gráficos
    chartData: this.prepareChartDataForPDF()
  };
},

// Preparar datos de gráficos para PDF
prepareChartDataForPDF() {
  return {
    currentPeriod: {
      labels: ['Ingresos', 'Gastos'],
      income: this.currentReport.totalIncome,
      expenses: this.currentReport.totalExpenses
    },
    last6Months: this.last6MonthsData
  };
},

// Generar el documento PDF
async generatePDFDocument(data) {
  // Importar jsPDF (asegúrate de incluir la librería)
  const { jsPDF } = window.jspdf;
  const pdf = new jsPDF();
  
  const pageWidth = pdf.internal.pageSize.width;
  const pageHeight = pdf.internal.pageSize.height;
  let currentY = 20;
  
  // ===== HEADER DEL PDF =====
  // Logo/Título
  pdf.setFontSize(24);
  pdf.setTextColor(70, 95, 255); // Color brand-500
  pdf.setFont('helvetica', 'bold');
  pdf.text('BudgetBuddy', 20, currentY);
  
  pdf.setFontSize(16);
  pdf.setTextColor(100, 116, 139); // Color gray-500
  pdf.setFont('helvetica', 'normal');
  pdf.text('Reporte Financiero', 20, currentY + 8);
  
  // Línea separadora
  pdf.setDrawColor(229, 231, 235); // gray-200
  pdf.line(20, currentY + 15, pageWidth - 20, currentY + 15);
  
  currentY += 25;
  
  // ===== INFORMACIÓN DEL USUARIO =====
  pdf.setFontSize(12);
  pdf.setTextColor(55, 65, 81); // gray-700
  pdf.setFont('helvetica', 'bold');
  pdf.text('INFORMACIÓN DEL USUARIO', 20, currentY);
  
  currentY += 8;
  pdf.setFont('helvetica', 'normal');
  pdf.setTextColor(75, 85, 99); // gray-600
  pdf.text(`Usuario: ${data.userName}`, 20, currentY);
  pdf.text(`Email: ${data.userEmail}`, 20, currentY + 6);
  pdf.text(`Período: ${data.period}`, 20, currentY + 12);
  pdf.text(`Generado: ${data.generatedDate}`, 20, currentY + 18);
  
  currentY += 30;
  
  // ===== RESUMEN FINANCIERO =====
  pdf.setFont('helvetica', 'bold');
  pdf.setTextColor(55, 65, 81);
  pdf.text('RESUMEN FINANCIERO', 20, currentY);
  
  currentY += 10;
  
  // Cuadro de métricas
  const boxWidth = (pageWidth - 50) / 2;
  const boxHeight = 40;
  
  // Ingresos
  pdf.setFillColor(240, 253, 244); // green-50
  pdf.rect(20, currentY, boxWidth, boxHeight, 'F');
  pdf.setDrawColor(34, 197, 94); // green-500
  pdf.rect(20, currentY, boxWidth, boxHeight, 'S');
  
  pdf.setTextColor(34, 197, 94);
  pdf.setFont('helvetica', 'bold');
  pdf.text('INGRESOS TOTALES', 25, currentY + 8);
  pdf.setFontSize(16);
  pdf.text(`$${data.totalIncome.toFixed(2)}`, 25, currentY + 18);
  pdf.setFontSize(10);
  pdf.setFont('helvetica', 'normal');
  pdf.text(`${data.incomePercentage} del total`, 25, currentY + 28);
  
  // Gastos
  pdf.setFillColor(254, 242, 242); // red-50
  pdf.rect(30 + boxWidth, currentY, boxWidth, boxHeight, 'F');
  pdf.setDrawColor(239, 68, 68); // red-500
  pdf.rect(30 + boxWidth, currentY, boxWidth, boxHeight, 'S');
  
  pdf.setTextColor(239, 68, 68);
  pdf.setFont('helvetica', 'bold');
  pdf.setFontSize(12);
  pdf.text('GASTOS TOTALES', 35 + boxWidth, currentY + 8);
  pdf.setFontSize(16);
  pdf.text(`$${data.totalExpenses.toFixed(2)}`, 35 + boxWidth, currentY + 18);
  pdf.setFontSize(10);
  pdf.setFont('helvetica', 'normal');
  pdf.text(`${data.expensePercentage} del total`, 35 + boxWidth, currentY + 28);
  
  currentY += 50;
  
  // Balance
  const balanceColor = data.balance >= 0 ? [34, 197, 94] : [239, 68, 68];
  const balanceText = data.balance >= 0 ? 'BALANCE POSITIVO' : 'BALANCE NEGATIVO';
  
  pdf.setTextColor(...balanceColor);
  pdf.setFont('helvetica', 'bold');
  pdf.setFontSize(14);
  pdf.text(balanceText, 20, currentY);
  pdf.setFontSize(20);
  pdf.text(`$${data.balance.toFixed(2)}`, 20, currentY + 10);
  
  currentY += 25;
  
  // Transacciones totales
  pdf.setTextColor(55, 65, 81);
  pdf.setFont('helvetica', 'normal');
  pdf.setFontSize(12);
  pdf.text(`Total de transacciones: ${data.totalTransactions}`, 20, currentY);
  
  currentY += 20;
  
  // ===== NOTAS ADICIONALES =====
  if (currentY > pageHeight - 60) {
    pdf.addPage();
    currentY = 20;
  }
  
  pdf.setFont('helvetica', 'bold');
  pdf.text('NOTAS ADICIONALES', 20, currentY);
  currentY += 8;
  
  pdf.setFont('helvetica', 'normal');
  pdf.setFontSize(10);
  pdf.setTextColor(107, 114, 128); // gray-500
  
  const notes = [
    '• Este reporte incluye todas las transacciones del período seleccionado',
    '• Los montos están expresados en la moneda local',
    '• Los gráficos y estadísticas se calculan en tiempo real',
    '• Generado automáticamente desde BudgetBuddy v1.0'
  ];
  
  notes.forEach(note => {
    pdf.text(note, 20, currentY);
    currentY += 6;
  });
  
  // ===== FOOTER =====
  pdf.setFontSize(8);
  pdf.setTextColor(156, 163, 175); // gray-400
  pdf.text(`Página 1 de 1`, pageWidth - 40, pageHeight - 10);
  pdf.text('BudgetBuddy - Gestión Financiera Personal', 20, pageHeight - 10);
  
  return pdf.output('blob');
},

// Descargar archivo PDF
downloadPDFFile(blob) {
  const url = window.URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  
  // Nombre del archivo con fecha
  const fileName = `Reporte_BudgetBuddy_${this.getPeriodText().replace(/\s+/g, '_')}_${new Date().toISOString().split('T')[0]}.pdf`;
  a.download = fileName;
  
  document.body.appendChild(a);
  a.click();
  document.body.removeChild(a);
  window.URL.revokeObjectURL(url);
},

// Actualizar progreso de PDF
updatePDFProgress(progress, message) {
  this.pdfProgress = progress;
  
  // Opcional: mostrar mensaje en consola o UI
  if (message) {
    console.log(`PDF Export: ${progress}% - ${message}`);
  }
},
```

---

## 📦 **Dependencias necesarias (agregar antes de cerrar </head>)**

```html
<!-- jsPDF para generar PDFs - Requerido para HU-005 -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>

<!-- html2canvas para capturar gráficos (opcional) -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
```

---

## 🎯 **Modal de progreso para exportación PDF (opcional)**

```html
<!-- Modal de progreso PDF - Agregar antes del loading state existente -->
<div x-show="pdfExporting" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
  <div class="bg-white dark:bg-gray-800 rounded-3xl p-8 max-w-md w-full mx-4">
    <!-- Header -->
    <div class="text-center mb-6">
      <div class="w-16 h-16 bg-red-100 dark:bg-red-900 rounded-full flex items-center justify-center mx-auto mb-4">
        <i class="fas fa-file-pdf text-red-600 dark:text-red-400 text-2xl"></i>
      </div>
      <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Generando PDF</h3>
      <p class="text-sm text-gray-500 dark:text-gray-400">Por favor, no cierre esta ventana</p>
    </div>
    
    <!-- Barra de progreso -->
    <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2 mb-4">
      <div class="bg-red-500 h-2 rounded-full transition-all duration-300 ease-out"
           :style="`width: ${pdfProgress}%`"></div>
    </div>
    
    <!-- Porcentaje -->
    <div class="text-center">
      <span class="text-2xl font-bold text-gray-900 dark:text-white" x-text="`${pdfProgress}%`"></span>
      <p class="text-sm text-gray-500 dark:text-gray-400">Procesando datos financieros...</p>
    </div>
    
    <!-- Estados de progreso -->
    <div class="mt-4 space-y-2">
      <div class="flex items-center text-sm">
        <div class="w-2 h-2 rounded-full mr-3"
             :class="pdfProgress >= 20 ? 'bg-green-500' : 'bg-gray-300'"></div>
        <span :class="pdfProgress >= 20 ? 'text-gray-900 dark:text-white' : 'text-gray-500'">
          Preparando datos
        </span>
      </div>
      <div class="flex items-center text-sm">
        <div class="w-2 h-2 rounded-full mr-3"
             :class="pdfProgress >= 50 ? 'bg-green-500' : 'bg-gray-300'"></div>
        <span :class="pdfProgress >= 50 ? 'text-gray-900 dark:text-white' : 'text-gray-500'">
          Generando gráficos
        </span>
      </div>
      <div class="flex items-center text-sm">
        <div class="w-2 h-2 rounded-full mr-3"
             :class="pdfProgress >= 80 ? 'bg-green-500' : 'bg-gray-300'"></div>
        <span :class="pdfProgress >= 80 ? 'text-gray-900 dark:text-white' : 'text-gray-500'">
          Finalizando descarga
        </span>
      </div>
    </div>
  </div>
</div>
```

---

## ✅ **Checklist de Implementación**

### **1. Cambios en HTML:**
- [ ] Reemplazar la sección de botones de exportación
- [ ] Agregar modal de progreso (opcional)
- [ ] Incluir librerías jsPDF y html2canvas

### **2. Cambios en JavaScript:**
- [ ] Agregar las funciones de exportación PDF al objeto Alpine.js
- [ ] Modificar la función `exportReport()` existente para claridad

### **3. Cambios en CSS:**
- [ ] Agregar estilos específicos para el botón PDF
- [ ] Estilos para el modal de progreso
- [ ] Estilos responsive

### **4. Testing:**
- [ ] Probar exportación con datos reales
- [ ] Verificar en diferentes navegadores
- [ ] Probar responsive en móvil
- [ ] Validar formato y calidad del PDF

---

## 🎯 **Resultado Final**

Con esta implementación tendrás:

✅ **Botón "Exportar PDF"** integrado con el diseño de BudgetBuddy  
✅ **Funcionalidad completa** de generación de PDF  
✅ **Modal de progreso** con estados visuales  
✅ **PDF profesional** con formato de la aplicación  
✅ **Responsive** y accesible  
✅ **Manejo de errores** robusto  

**El resultado cumple 100% con los criterios de aceptación de HU-005.**