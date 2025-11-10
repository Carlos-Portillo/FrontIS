# HU-005: HTML y CSS para Code to Design (Figma)

## Encargado: Carlos César Portillo Mendoza

---

## 📄 **HTML Optimizado para Code to Design Plugin**

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BudgetBuddy - Reportes</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
</head>
<body>
    <div class="container">
        <!-- Header -->
        <header class="header">
            <h1 class="title">
                <i class="fas fa-chart-line icon-title"></i>
                Reportes Financieros - BudgetBuddy
            </h1>
            <p class="subtitle">Análisis detallado de tu estado financiero</p>
        </header>

        <!-- Filtros -->
        <section class="filters-section">
            <h3 class="section-title">
                <i class="fas fa-filter icon-section"></i>
                Seleccionar Período
            </h3>
            <div class="filters-grid">
                <div class="filter-item">
                    <label>Tipo de reporte</label>
                    <select class="select-input">
                        <option>General</option>
                        <option>Por año</option>
                        <option>Por mes</option>
                    </select>
                </div>
                <div class="filter-item">
                    <label>Año</label>
                    <select class="select-input">
                        <option>2025</option>
                        <option>2024</option>
                    </select>
                </div>
                <div class="filter-item">
                    <label>Mes</label>
                    <select class="select-input">
                        <option>Noviembre</option>
                        <option>Octubre</option>
                    </select>
                </div>
                <div class="filter-item">
                    <button class="btn-generate">
                        <i class="fas fa-sync-alt"></i>
                        Generar
                    </button>
                </div>
            </div>
        </section>

        <!-- Métricas -->
        <section class="metrics-section">
            <div class="metric-card metric-income">
                <div class="metric-icon">
                    <i class="fas fa-arrow-up"></i>
                </div>
                <div class="metric-content">
                    <p class="metric-label">Total Ingresos</p>
                    <p class="metric-value">$3,250.00</p>
                    <p class="metric-change positive">+12.5%</p>
                </div>
            </div>

            <div class="metric-card metric-expenses">
                <div class="metric-icon">
                    <i class="fas fa-arrow-down"></i>
                </div>
                <div class="metric-content">
                    <p class="metric-label">Total Gastos</p>
                    <p class="metric-value">$1,890.50</p>
                    <p class="metric-change negative">+5.8%</p>
                </div>
            </div>

            <div class="metric-card metric-balance">
                <div class="metric-icon">
                    <i class="fas fa-chart-line"></i>
                </div>
                <div class="metric-content">
                    <p class="metric-label">Balance</p>
                    <p class="metric-value positive">$1,359.50</p>
                    <p class="metric-change positive">Positivo ↗</p>
                </div>
            </div>

            <div class="metric-card metric-transactions">
                <div class="metric-icon">
                    <i class="fas fa-receipt"></i>
                </div>
                <div class="metric-content">
                    <p class="metric-label">Transacciones</p>
                    <p class="metric-value">47</p>
                    <p class="metric-change">Este mes</p>
                </div>
            </div>
        </section>

        <!-- Gráficos -->
        <section class="charts-section">
            <div class="chart-card">
                <h3 class="chart-title">
                    <i class="fas fa-chart-pie"></i>
                    Distribución Actual
                </h3>
                <div class="chart-placeholder">
                    <i class="fas fa-chart-pie chart-icon"></i>
                    <p>Gráfico de distribución</p>
                    <span>Ingresos vs Gastos</span>
                </div>
            </div>

            <div class="chart-card">
                <h3 class="chart-title">
                    <i class="fas fa-chart-line"></i>
                    Últimos 6 Meses
                </h3>
                <div class="chart-placeholder">
                    <i class="fas fa-chart-line chart-icon"></i>
                    <p>Tendencia de gastos</p>
                    <span>Evolución mensual</span>
                </div>
            </div>
        </section>

        <!-- Tabla de Transacciones -->
        <section class="transactions-section">
            <h3 class="section-title">
                <i class="fas fa-list"></i>
                Detalle de Transacciones
            </h3>
            <div class="table-container">
                <table class="transactions-table">
                    <thead>
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
                            <td><span class="badge badge-food">Alimentación</span></td>
                            <td class="amount negative">-$85.50</td>
                        </tr>
                        <tr>
                            <td>02/11/2025</td>
                            <td>Salario Noviembre</td>
                            <td><span class="badge badge-income">Ingreso</span></td>
                            <td class="amount positive">+$2,500.00</td>
                        </tr>
                        <tr>
                            <td>03/11/2025</td>
                            <td>Gasolina Shell</td>
                            <td><span class="badge badge-transport">Transporte</span></td>
                            <td class="amount negative">-$45.00</td>
                        </tr>
                        <tr>
                            <td>04/11/2025</td>
                            <td>Netflix</td>
                            <td><span class="badge badge-entertainment">Entretenimiento</span></td>
                            <td class="amount negative">-$15.99</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <!-- SECCIÓN DE EXPORTACIÓN - HU-005 -->
        <section class="export-section">
            <h3 class="export-title">
                <i class="fas fa-download"></i>
                Exportar Reportes
            </h3>
            <p class="export-description">
                Descarga tus datos financieros en diferentes formatos
            </p>

            <div class="export-buttons">
                <!-- Botón Excel -->
                <button class="export-btn excel-btn">
                    <i class="fas fa-file-excel"></i>
                    <div class="btn-content">
                        <span class="btn-title">Exportar Excel</span>
                        <span class="btn-subtitle">Formato .xlsx</span>
                    </div>
                </button>

                <!-- BOTÓN PDF - HU-005 -->
                <button class="export-btn pdf-btn">
                    <i class="fas fa-file-pdf"></i>
                    <div class="btn-content">
                        <span class="btn-title">Exportar PDF</span>
                        <span class="btn-subtitle">Formato profesional</span>
                    </div>
                    <span class="new-badge">✨ NUEVO</span>
                </button>
            </div>

            <!-- Información -->
            <div class="export-info">
                <div class="info-content">
                    <i class="fas fa-info-circle info-icon"></i>
                    <div>
                        <h4>Sobre la exportación PDF</h4>
                        <ul>
                            <li>Incluye todos los datos visibles en pantalla</li>
                            <li>Mantiene formato profesional y colores</li>
                            <li>Contiene gráficos, tablas y resumen financiero</li>
                            <li>Listo para imprimir o enviar por email</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>
    </div>
</body>
</html>
```

---

## 🎨 **CSS Optimizado para Figma**

```css
/* Reset y base */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    background-color: #f8fafc;
    color: #1e293b;
    line-height: 1.6;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 24px;
    background: white;
}

/* Header */
.header {
    text-align: center;
    margin-bottom: 32px;
    padding: 24px;
    background: linear-gradient(135deg, #465fff 0%, #3641f5 100%);
    border-radius: 16px;
    color: white;
}

.title {
    font-size: 28px;
    font-weight: 700;
    margin-bottom: 8px;
}

.subtitle {
    font-size: 16px;
    opacity: 0.9;
}

.icon-title {
    margin-right: 12px;
    font-size: 24px;
}

/* Filtros */
.filters-section {
    background: white;
    border-radius: 16px;
    padding: 24px;
    margin-bottom: 32px;
    border: 1px solid #e2e8f0;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.section-title {
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 16px;
    color: #1e293b;
}

.icon-section {
    margin-right: 8px;
    color: #465fff;
}

.filters-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
    align-items: end;
}

.filter-item label {
    display: block;
    font-size: 14px;
    font-weight: 500;
    margin-bottom: 6px;
    color: #374151;
}

.select-input {
    width: 100%;
    padding: 12px 16px;
    border: 1px solid #d1d5db;
    border-radius: 8px;
    font-size: 14px;
    background: white;
}

.btn-generate {
    width: 100%;
    padding: 12px 16px;
    background: #465fff;
    color: white;
    border: none;
    border-radius: 8px;
    font-weight: 500;
    cursor: pointer;
}

.btn-generate i {
    margin-right: 8px;
}

/* Métricas */
.metrics-section {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin-bottom: 32px;
}

.metric-card {
    background: white;
    border-radius: 16px;
    padding: 24px;
    border: 1px solid #e2e8f0;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
    display: flex;
    align-items: center;
}

.metric-icon {
    width: 48px;
    height: 48px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    margin-right: 16px;
}

.metric-income .metric-icon {
    background: #dcfce7;
    color: #16a34a;
}

.metric-expenses .metric-icon {
    background: #fee2e2;
    color: #dc2626;
}

.metric-balance .metric-icon {
    background: #dbeafe;
    color: #2563eb;
}

.metric-transactions .metric-icon {
    background: #f3e8ff;
    color: #9333ea;
}

.metric-label {
    font-size: 14px;
    color: #64748b;
    margin-bottom: 4px;
}

.metric-value {
    font-size: 24px;
    font-weight: 700;
    color: #1e293b;
    margin-bottom: 4px;
}

.metric-change {
    font-size: 12px;
    font-weight: 500;
}

.positive {
    color: #16a34a;
}

.negative {
    color: #dc2626;
}

/* Gráficos */
.charts-section {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    gap: 24px;
    margin-bottom: 32px;
}

.chart-card {
    background: white;
    border-radius: 16px;
    padding: 24px;
    border: 1px solid #e2e8f0;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.chart-title {
    font-size: 16px;
    font-weight: 600;
    margin-bottom: 16px;
    color: #1e293b;
}

.chart-title i {
    margin-right: 8px;
    color: #465fff;
}

.chart-placeholder {
    height: 200px;
    background: #f8fafc;
    border-radius: 12px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #64748b;
}

.chart-icon {
    font-size: 48px;
    margin-bottom: 12px;
    color: #cbd5e1;
}

.chart-placeholder p {
    font-size: 16px;
    font-weight: 500;
    margin-bottom: 4px;
}

.chart-placeholder span {
    font-size: 14px;
}

/* Tabla */
.transactions-section {
    background: white;
    border-radius: 16px;
    padding: 24px;
    margin-bottom: 32px;
    border: 1px solid #e2e8f0;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.table-container {
    overflow-x: auto;
    margin-top: 16px;
}

.transactions-table {
    width: 100%;
    border-collapse: collapse;
}

.transactions-table th {
    text-align: left;
    padding: 12px;
    border-bottom: 2px solid #e2e8f0;
    font-weight: 600;
    color: #374151;
    font-size: 14px;
}

.transactions-table td {
    padding: 12px;
    border-bottom: 1px solid #f1f5f9;
    font-size: 14px;
}

.transactions-table tr:hover {
    background: #f8fafc;
}

.badge {
    padding: 4px 12px;
    border-radius: 12px;
    font-size: 12px;
    font-weight: 500;
    text-align: center;
    display: inline-block;
}

.badge-food {
    background: #dbeafe;
    color: #1d4ed8;
}

.badge-income {
    background: #dcfce7;
    color: #166534;
}

.badge-transport {
    background: #fef3c7;
    color: #92400e;
}

.badge-entertainment {
    background: #f3e8ff;
    color: #7c2d12;
}

.amount {
    font-weight: 600;
    text-align: right;
}

/* SECCIÓN DE EXPORTACIÓN - HU-005 */
.export-section {
    background: white;
    border-radius: 16px;
    padding: 32px;
    text-align: center;
    border: 1px solid #e2e8f0;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.export-title {
    font-size: 20px;
    font-weight: 600;
    margin-bottom: 8px;
    color: #1e293b;
}

.export-title i {
    margin-right: 12px;
    color: #465fff;
}

.export-description {
    color: #64748b;
    margin-bottom: 32px;
    font-size: 16px;
}

.export-buttons {
    display: flex;
    flex-direction: column;
    gap: 20px;
    align-items: center;
    margin-bottom: 32px;
}

/* Botones de exportación */
.export-btn {
    display: flex;
    align-items: center;
    padding: 20px 32px;
    border: none;
    border-radius: 16px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    position: relative;
    min-width: 280px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    transition: all 0.3s ease;
}

.export-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

.export-btn i {
    font-size: 24px;
    margin-right: 16px;
}

.btn-content {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    text-align: left;
}

.btn-title {
    font-size: 16px;
    font-weight: 600;
    line-height: 1.2;
}

.btn-subtitle {
    font-size: 12px;
    opacity: 0.8;
    font-weight: 400;
}

/* Botón Excel */
.excel-btn {
    background: linear-gradient(135deg, #10b981 0%, #059669 100%);
    color: white;
}

.excel-btn:hover {
    background: linear-gradient(135deg, #059669 0%, #047857 100%);
}

/* BOTÓN PDF - HU-005 */
.pdf-btn {
    background: linear-gradient(135deg, #ef4444 0%, #dc2626 100%);
    color: white;
}

.pdf-btn:hover {
    background: linear-gradient(135deg, #dc2626 0%, #b91c1c 100%);
}

/* Badge NUEVO */
.new-badge {
    position: absolute;
    top: -8px;
    right: -8px;
    background: linear-gradient(135deg, #f59e0b 0%, #d97706 100%);
    color: white;
    font-size: 10px;
    font-weight: 700;
    padding: 4px 10px;
    border-radius: 12px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    box-shadow: 0 2px 8px rgba(245, 158, 11, 0.4);
}

/* Información adicional */
.export-info {
    background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%);
    border: 1px solid #bfdbfe;
    border-radius: 12px;
    padding: 20px;
}

.info-content {
    display: flex;
    align-items: flex-start;
    text-align: left;
}

.info-icon {
    color: #2563eb;
    font-size: 20px;
    margin-right: 16px;
    margin-top: 2px;
}

.info-content h4 {
    font-size: 16px;
    font-weight: 600;
    color: #1e40af;
    margin-bottom: 8px;
}

.info-content ul {
    list-style: none;
    color: #1e40af;
}

.info-content li {
    font-size: 14px;
    margin-bottom: 4px;
    padding-left: 0;
}

.info-content li:before {
    content: "• ";
    color: #2563eb;
    font-weight: 600;
    margin-right: 8px;
}

/* Responsive para dispositivos pequeños */
@media (max-width: 640px) {
    .container {
        padding: 16px;
    }
    
    .filters-grid {
        grid-template-columns: 1fr;
    }
    
    .metrics-section {
        grid-template-columns: 1fr;
    }
    
    .charts-section {
        grid-template-columns: 1fr;
    }
    
    .export-buttons {
        flex-direction: column;
        gap: 16px;
    }
    
    .export-btn {
        min-width: 100%;
    }
    
    .info-content {
        flex-direction: column;
    }
    
    .info-icon {
        margin-bottom: 8px;
        margin-right: 0;
    }
}

/* Para pantallas medianas */
@media (min-width: 641px) and (max-width: 1024px) {
    .export-buttons {
        flex-direction: row;
        justify-content: center;
        gap: 24px;
    }
}

/* Para pantallas grandes */
@media (min-width: 1025px) {
    .export-buttons {
        flex-direction: row;
        justify-content: center;
        gap: 32px;
    }
    
    .export-btn {
        min-width: 300px;
    }
}
```

---

## ✅ **Características del código para Figma:**

### **🎯 Optimizado para Code to Design:**
- ✅ **Sin JavaScript** - Solo HTML y CSS puro
- ✅ **Sin modales** - Todo visible en una sola página
- ✅ **Estructura limpia** - Fácil de convertir en componentes
- ✅ **Clases descriptivas** - Nombres claros para el plugin

### **🎨 Diseño Visual Completo:**
- ✅ **Header** con gradiente azul de BudgetBuddy
- ✅ **Filtros** con selects estilizados
- ✅ **Métricas** en cards con iconos y colores
- ✅ **Gráficos** con placeholders visuales
- ✅ **Tabla** de transacciones con badges
- ✅ **Botones de exportación** - Excel verde + PDF rojo con badge "NUEVO"
- ✅ **Información contextual** en caja azul

### **📱 Responsive:**
- ✅ **Mobile:** Layout vertical optimizado
- ✅ **Tablet:** Grid adaptativo
- ✅ **Desktop:** Diseño completo con efectos

### **🎯 Resultado en Figma:**
Este código generará automáticamente un diseño visual completo de la página de reportes con el botón PDF destacado, perfecto para presentar la HU-005.

**¡Copia y pega directamente en el plugin Code to Design de Figma!**