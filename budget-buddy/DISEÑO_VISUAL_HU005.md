# Diseño Visual HU-005 - Enlaces Directos

## 🎨 **Opción 1: Excalidraw (Recomendado - Más Fácil)**

### **Enlace directo al diseño:**
👉 **Copia y pega este JSON en Excalidraw.com:**

```json
{
  "type": "excalidraw",
  "version": 2,
  "elements": [
    {
      "type": "rectangle",
      "x": 100,
      "y": 100,
      "width": 600,
      "height": 60,
      "fill": "#007bff",
      "strokeColor": "#007bff",
      "text": "🏦 BudgetBuddy - Reportes Financieros"
    },
    {
      "type": "rectangle", 
      "x": 100,
      "y": 180,
      "width": 600,
      "height": 80,
      "fill": "#f8f9fa",
      "strokeColor": "#ddd",
      "text": "🔍 Filtros: 📅 Desde-Hasta | 🏷️ Categorías"
    },
    {
      "type": "rectangle",
      "x": 100, 
      "y": 280,
      "width": 600,
      "height": 200,
      "fill": "#e8f5e8",
      "strokeColor": "#28a745",
      "text": "📊 GRÁFICO DE TENDENCIA\n(Chart.js interactivo)"
    },
    {
      "type": "rectangle",
      "x": 100,
      "y": 500,
      "width": 600, 
      "height": 250,
      "fill": "#ffffff",
      "strokeColor": "#ddd",
      "text": "📋 TABLA DE TRANSACCIONES\nFecha | Descripción | Categoría | Monto\n01/11 | Supermercado | Alimentación | -$85.50\n02/11 | Salario | Ingreso | +$2,500"
    },
    {
      "type": "rectangle",
      "x": 200,
      "y": 770,
      "width": 150,
      "height": 50,
      "fill": "#28a745",
      "strokeColor": "#28a745",
      "text": "📊 Exportar Excel"
    },
    {
      "type": "rectangle",
      "x": 370,
      "y": 770, 
      "width": 150,
      "height": 50,
      "fill": "#dc3545",
      "strokeColor": "#dc3545", 
      "text": "📄 Exportar PDF"
    },
    {
      "type": "arrow",
      "x": 445,
      "y": 750,
      "endX": 445,
      "endY": 770,
      "strokeColor": "#ff0000"
    },
    {
      "type": "text",
      "x": 380,
      "y": 730,
      "text": "✨ NUEVA FUNCIONALIDAD",
      "fontSize": 14,
      "color": "#dc3545"
    }
  ]
}
```

**Pasos para usarlo:**
1. Ve a **https://excalidraw.com/**
2. Haz clic en "Open" (abrir)
3. Pega el JSON de arriba
4. ¡Listo! Ya tienes el diseño visual

---

## 🎨 **Opción 2: CodePen (Diseño Interactivo)**

### **Enlace directo:**
👉 **Ve a CodePen.io y crea un nuevo pen con este código:**

**HTML:**
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HU-005: Exportar PDF - BudgetBuddy</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body class="bg-light">
    <div class="container-fluid">
        <!-- Header -->
        <div class="bg-primary text-white text-center py-3 mb-4">
            <h1 class="mb-0">🏦 BudgetBuddy - Reportes Financieros</h1>
        </div>

        <!-- Filtros -->
        <div class="card mb-4">
            <div class="card-body">
                <h5 class="card-title">🔍 Filtros de Búsqueda</h5>
                <div class="row">
                    <div class="col-md-4">
                        <label class="form-label">📅 Desde:</label>
                        <input type="date" class="form-control" value="2025-11-01">
                    </div>
                    <div class="col-md-4">
                        <label class="form-label">📅 Hasta:</label>
                        <input type="date" class="form-control" value="2025-11-30">
                    </div>
                    <div class="col-md-4">
                        <label class="form-label">🏷️ Categorías:</label>
                        <select class="form-control">
                            <option>Todas las categorías</option>
                            <option>Alimentación</option>
                            <option>Transporte</option>
                            <option>Entretenimiento</option>
                        </select>
                    </div>
                </div>
            </div>
        </div>

        <!-- Gráfico -->
        <div class="card mb-4">
            <div class="card-body">
                <h5 class="card-title">📊 Tendencia de Gastos (Últimos 6 meses)</h5>
                <canvas id="gastosChart" width="400" height="200"></canvas>
            </div>
        </div>

        <!-- Tabla de Transacciones -->
        <div class="card mb-4">
            <div class="card-body">
                <h5 class="card-title">📋 Detalle de Transacciones</h5>
                <div class="table-responsive">
                    <table class="table table-striped">
                        <thead class="table-primary">
                            <tr>
                                <th>Fecha</th>
                                <th>Descripción</th>
                                <th>Categoría</th>
                                <th>Monto</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>01/11/2025</td>
                                <td>Supermercado Metro</td>
                                <td><span class="badge bg-info">Alimentación</span></td>
                                <td class="text-danger">-$85.50</td>
                            </tr>
                            <tr>
                                <td>02/11/2025</td>
                                <td>Salario Noviembre</td>
                                <td><span class="badge bg-success">Ingreso</span></td>
                                <td class="text-success">+$2,500.00</td>
                            </tr>
                            <tr>
                                <td>03/11/2025</td>
                                <td>Gasolina Shell</td>
                                <td><span class="badge bg-warning">Transporte</span></td>
                                <td class="text-danger">-$45.00</td>
                            </tr>
                            <tr>
                                <td>04/11/2025</td>
                                <td>Netflix</td>
                                <td><span class="badge bg-purple">Entretenimiento</span></td>
                                <td class="text-danger">-$15.99</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

        <!-- Botones de Exportación -->
        <div class="card">
            <div class="card-body text-center">
                <h5 class="card-title">📤 Exportar Reportes</h5>
                <p class="text-muted">Descarga tus datos en diferentes formatos</p>
                
                <button class="btn btn-success btn-lg me-3" onclick="exportarExcel()">
                    📊 Exportar Excel
                </button>
                
                <button class="btn btn-danger btn-lg position-relative" onclick="exportarPDF()">
                    📄 Exportar PDF
                    <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-warning text-dark">
                        ✨ NUEVO
                    </span>
                </button>
                
                <div class="mt-3">
                    <small class="text-muted">
                        💡 El PDF incluirá todos los datos mostrados en pantalla con formato profesional
                    </small>
                </div>
            </div>
        </div>

        <!-- Modal de Loading -->
        <div class="modal" id="loadingModal" tabindex="-1">
            <div class="modal-dialog modal-dialog-centered">
                <div class="modal-content">
                    <div class="modal-body text-center">
                        <div class="spinner-border text-primary" role="status">
                            <span class="visually-hidden">Loading...</span>
                        </div>
                        <h5 class="mt-3">⏳ Generando PDF...</h5>
                        <p class="text-muted">Por favor, no cierre esta ventana</p>
                        <div class="progress">
                            <div class="progress-bar bg-danger progress-bar-animated" style="width: 65%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```

**CSS:**
```css
.badge.bg-purple {
    background-color: #6f42c1 !important;
}

.btn-lg {
    padding: 12px 30px;
    font-size: 1.1rem;
}

.card {
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    border: none;
    border-radius: 10px;
}

.table th {
    border-top: none;
}

.progress {
    height: 10px;
    margin-top: 15px;
}

.btn-danger:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 15px rgba(220,53,69,0.3);
    transition: all 0.3s ease;
}

#gastosChart {
    max-height: 300px;
}
```

**JavaScript:**
```javascript
// Configurar gráfico
const ctx = document.getElementById('gastosChart').getContext('2d');
new Chart(ctx, {
    type: 'line',
    data: {
        labels: ['Jun', 'Jul', 'Ago', 'Sep', 'Oct', 'Nov'],
        datasets: [{
            label: 'Gastos Mensuales',
            data: [1200, 1100, 1350, 1000, 1450, 1250],
            borderColor: '#dc3545',
            backgroundColor: 'rgba(220,53,69,0.1)',
            tension: 0.4
        }]
    },
    options: {
        responsive: true,
        plugins: {
            title: {
                display: true,
                text: 'Tendencia de Gastos - Últimos 6 Meses'
            }
        },
        scales: {
            y: {
                beginAtZero: true,
                ticks: {
                    callback: function(value) {
                        return '$' + value;
                    }
                }
            }
        }
    }
});

function exportarExcel() {
    alert('📊 Funcionalidad de Excel ya implementada');
}

function exportarPDF() {
    // Mostrar modal de loading
    const modal = new bootstrap.Modal(document.getElementById('loadingModal'));
    modal.show();
    
    // Simular proceso de generación
    setTimeout(() => {
        modal.hide();
        alert('✅ ¡PDF generado exitosamente!\n\n📄 Archivo: Reporte_BudgetBuddy_Nov2025.pdf\n📦 Tamaño: 2.3 MB\n\n✨ El archivo se ha descargado automáticamente');
    }, 3000);
}
```

---

## 🚀 **Opción 3: Figma con Plugin HTML-CSS**

### **Pasos rápidos:**
1. Abre **Figma.com**
2. Instala el plugin **"HTML to Design"**
3. Pega el código HTML de arriba
4. ¡Se convierte automáticamente en diseño visual!

---

## 📱 **Opción 4: Crear mockup con IA (Más Moderno)**

Puedes usar estos prompts en **Midjourney**, **DALL-E** o **Stable Diffusion**:

```
"Web dashboard interface for financial app, showing expense reports with export PDF button highlighted in red, clean modern UI, Bootstrap style, professional layout, charts and data tables visible"
```

---

## 🎯 **Mi Recomendación:**

**Para presentación rápida:** Usa **CodePen** con el código que te di
**Para diseño colaborativo:** Usa **Excalidraw** con el JSON
**Para presentación profesional:** Figma con plugin HTML

¿Cuál prefieres que detalle más o te ayudo a implementar?