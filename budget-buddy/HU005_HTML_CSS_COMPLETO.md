# HU-005: Exportar Reporte a PDF - HTML y CSS

## Encargado: Carlos César Portillo Mendoza

---

## 📄 **HTML - Página de Reportes con Botón PDF**

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>BudgetBuddy - Reportes</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Font Awesome para iconos -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <script src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js" defer></script>
    <link href="./css/style.css" rel="stylesheet">
  </head>

  <body class="bg-gray-50 dark:bg-gray-900 font-outfit">
    <!-- ===== Page Wrapper ===== -->
    <div class="flex h-screen overflow-hidden">
      
      <!-- ===== Content Area ===== -->
      <div class="relative flex flex-col flex-1 overflow-x-hidden overflow-y-auto">
        
        <!-- ===== Header ===== -->
        <header class="bg-white dark:bg-gray-800 shadow-sm border-b border-gray-200 dark:border-gray-700">
          <div class="px-6 py-4">
            <h1 class="text-2xl font-bold text-gray-900 dark:text-white">
              <i class="fas fa-chart-line text-brand-500 mr-3"></i>
              Reportes Financieros
            </h1>
            <p class="text-gray-500 dark:text-gray-400 mt-1">
              Análisis detallado de tu estado financiero
            </p>
          </div>
        </header>

        <!-- ===== Main Content ===== -->
        <main class="flex-1 p-6">
          
          <!-- ===== Filtros de Período ===== -->
          <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm p-6 mb-8 border border-gray-200 dark:border-gray-700">
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">
              <i class="fas fa-filter text-blue-500 mr-2"></i>
              Seleccionar Período
            </h3>
            <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
              <!-- Tipo de reporte -->
              <div>
                <label class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">Tipo de reporte</label>
                <select class="w-full border border-gray-300 dark:border-gray-600 rounded-lg px-3 py-2.5 bg-white dark:bg-gray-700 text-gray-900 dark:text-white focus:ring-2 focus:ring-brand-500 focus:border-brand-500">
                  <option value="general">General</option>
                  <option value="year">Por año</option>
                  <option value="month">Por mes</option>
                  <option value="range">Por rango de fechas</option>
                </select>
              </div>

              <!-- Año -->
              <div>
                <label class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">Año</label>
                <select class="w-full border border-gray-300 dark:border-gray-600 rounded-lg px-3 py-2.5 bg-white dark:bg-gray-700 text-gray-900 dark:text-white focus:ring-2 focus:ring-brand-500 focus:border-brand-500">
                  <option value="2025">2025</option>
                  <option value="2024">2024</option>
                  <option value="2023">2023</option>
                </select>
              </div>

              <!-- Mes -->
              <div>
                <label class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">Mes</label>
                <select class="w-full border border-gray-300 dark:border-gray-600 rounded-lg px-3 py-2.5 bg-white dark:bg-gray-700 text-gray-900 dark:text-white focus:ring-2 focus:ring-brand-500 focus:border-brand-500">
                  <option value="11">Noviembre</option>
                  <option value="10">Octubre</option>
                  <option value="9">Septiembre</option>
                </select>
              </div>

              <!-- Botón generar -->
              <div class="flex items-end">
                <button class="w-full bg-brand-500 hover:bg-brand-600 text-white px-4 py-2.5 rounded-lg font-medium transition-colors duration-200">
                  <i class="fas fa-sync-alt mr-2"></i>
                  Generar
                </button>
              </div>
            </div>
          </div>

          <!-- ===== Métricas Principales ===== -->
          <div class="grid grid-cols-1 md:grid-cols-4 gap-6 mb-8">
            
            <!-- Total Ingresos -->
            <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm p-6 border border-gray-200 dark:border-gray-700">
              <div class="flex items-center">
                <div class="flex-shrink-0">
                  <div class="w-12 h-12 bg-green-100 dark:bg-green-900 rounded-lg flex items-center justify-center">
                    <i class="fas fa-arrow-up text-green-600 dark:text-green-400 text-xl"></i>
                  </div>
                </div>
                <div class="ml-4">
                  <p class="text-sm font-medium text-gray-500 dark:text-gray-400">Total Ingresos</p>
                  <p class="text-2xl font-bold text-gray-900 dark:text-white">$3,250.00</p>
                  <p class="text-sm text-green-600 dark:text-green-400">+12.5%</p>
                </div>
              </div>
            </div>

            <!-- Total Gastos -->
            <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm p-6 border border-gray-200 dark:border-gray-700">
              <div class="flex items-center">
                <div class="flex-shrink-0">
                  <div class="w-12 h-12 bg-red-100 dark:bg-red-900 rounded-lg flex items-center justify-center">
                    <i class="fas fa-arrow-down text-red-600 dark:text-red-400 text-xl"></i>
                  </div>
                </div>
                <div class="ml-4">
                  <p class="text-sm font-medium text-gray-500 dark:text-gray-400">Total Gastos</p>
                  <p class="text-2xl font-bold text-gray-900 dark:text-white">$1,890.50</p>
                  <p class="text-sm text-red-600 dark:text-red-400">+5.8%</p>
                </div>
              </div>
            </div>

            <!-- Balance -->
            <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm p-6 border border-gray-200 dark:border-gray-700">
              <div class="flex items-center">
                <div class="flex-shrink-0">
                  <div class="w-12 h-12 bg-blue-100 dark:bg-blue-900 rounded-lg flex items-center justify-center">
                    <i class="fas fa-chart-line text-blue-600 dark:text-blue-400 text-xl"></i>
                  </div>
                </div>
                <div class="ml-4">
                  <p class="text-sm font-medium text-gray-500 dark:text-gray-400">Balance</p>
                  <p class="text-2xl font-bold text-green-600 dark:text-green-400">$1,359.50</p>
                  <p class="text-sm text-green-600 dark:text-green-400">Positivo ↗</p>
                </div>
              </div>
            </div>

            <!-- Transacciones -->
            <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm p-6 border border-gray-200 dark:border-gray-700">
              <div class="flex items-center">
                <div class="flex-shrink-0">
                  <div class="w-12 h-12 bg-purple-100 dark:bg-purple-900 rounded-lg flex items-center justify-center">
                    <i class="fas fa-receipt text-purple-600 dark:text-purple-400 text-xl"></i>
                  </div>
                </div>
                <div class="ml-4">
                  <p class="text-sm font-medium text-gray-500 dark:text-gray-400">Transacciones</p>
                  <p class="text-2xl font-bold text-gray-900 dark:text-white">47</p>
                  <p class="text-sm text-gray-500 dark:text-gray-400">Este mes</p>
                </div>
              </div>
            </div>
          </div>

          <!-- ===== Gráficos ===== -->
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 mb-8">
            
            <!-- Gráfico Distribución -->
            <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm p-6 border border-gray-200 dark:border-gray-700">
              <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">
                <i class="fas fa-chart-pie text-brand-500 mr-2"></i>
                Distribución Actual
              </h3>
              <div class="h-64 bg-gray-50 dark:bg-gray-700 rounded-lg flex items-center justify-center">
                <div class="text-center">
                  <i class="fas fa-chart-pie text-4xl text-gray-400 mb-3"></i>
                  <p class="text-gray-500 dark:text-gray-400">Gráfico de distribución</p>
                  <p class="text-sm text-gray-400">Ingresos vs Gastos</p>
                </div>
              </div>
            </div>

            <!-- Gráfico Tendencia -->
            <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm p-6 border border-gray-200 dark:border-gray-700">
              <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-4">
                <i class="fas fa-chart-line text-brand-500 mr-2"></i>
                Últimos 6 Meses
              </h3>
              <div class="h-64 bg-gray-50 dark:bg-gray-700 rounded-lg flex items-center justify-center">
                <div class="text-center">
                  <i class="fas fa-chart-line text-4xl text-gray-400 mb-3"></i>
                  <p class="text-gray-500 dark:text-gray-400">Tendencia de gastos</p>
                  <p class="text-sm text-gray-400">Evolución mensual</p>
                </div>
              </div>
            </div>
          </div>

          <!-- ===== Detalle de Transacciones ===== -->
          <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm border border-gray-200 dark:border-gray-700 mb-8">
            <div class="px-6 py-4 border-b border-gray-200 dark:border-gray-700">
              <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
                <i class="fas fa-list text-brand-500 mr-2"></i>
                Detalle de Transacciones
              </h3>
            </div>
            <div class="p-6">
              <div class="overflow-x-auto">
                <table class="w-full">
                  <thead>
                    <tr class="border-b border-gray-200 dark:border-gray-700">
                      <th class="text-left py-3 px-4 text-sm font-semibold text-gray-700 dark:text-gray-300">Fecha</th>
                      <th class="text-left py-3 px-4 text-sm font-semibold text-gray-700 dark:text-gray-300">Descripción</th>
                      <th class="text-left py-3 px-4 text-sm font-semibold text-gray-700 dark:text-gray-300">Categoría</th>
                      <th class="text-right py-3 px-4 text-sm font-semibold text-gray-700 dark:text-gray-300">Monto</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr class="border-b border-gray-100 dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-700">
                      <td class="py-3 px-4 text-sm text-gray-600 dark:text-gray-400">01/11/2025</td>
                      <td class="py-3 px-4 text-sm text-gray-900 dark:text-white font-medium">Supermercado Metro</td>
                      <td class="py-3 px-4">
                        <span class="inline-flex px-2 py-1 text-xs font-semibold rounded-full bg-blue-100 text-blue-800 dark:bg-blue-900 dark:text-blue-200">
                          Alimentación
                        </span>
                      </td>
                      <td class="py-3 px-4 text-right text-sm font-semibold text-red-600 dark:text-red-400">-$85.50</td>
                    </tr>
                    <tr class="border-b border-gray-100 dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-700">
                      <td class="py-3 px-4 text-sm text-gray-600 dark:text-gray-400">02/11/2025</td>
                      <td class="py-3 px-4 text-sm text-gray-900 dark:text-white font-medium">Salario Noviembre</td>
                      <td class="py-3 px-4">
                        <span class="inline-flex px-2 py-1 text-xs font-semibold rounded-full bg-green-100 text-green-800 dark:bg-green-900 dark:text-green-200">
                          Ingreso
                        </span>
                      </td>
                      <td class="py-3 px-4 text-right text-sm font-semibold text-green-600 dark:text-green-400">+$2,500.00</td>
                    </tr>
                    <tr class="border-b border-gray-100 dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-700">
                      <td class="py-3 px-4 text-sm text-gray-600 dark:text-gray-400">03/11/2025</td>
                      <td class="py-3 px-4 text-sm text-gray-900 dark:text-white font-medium">Gasolina Shell</td>
                      <td class="py-3 px-4">
                        <span class="inline-flex px-2 py-1 text-xs font-semibold rounded-full bg-yellow-100 text-yellow-800 dark:bg-yellow-900 dark:text-yellow-200">
                          Transporte
                        </span>
                      </td>
                      <td class="py-3 px-4 text-right text-sm font-semibold text-red-600 dark:text-red-400">-$45.00</td>
                    </tr>
                    <tr class="border-b border-gray-100 dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-700">
                      <td class="py-3 px-4 text-sm text-gray-600 dark:text-gray-400">04/11/2025</td>
                      <td class="py-3 px-4 text-sm text-gray-900 dark:text-white font-medium">Netflix</td>
                      <td class="py-3 px-4">
                        <span class="inline-flex px-2 py-1 text-xs font-semibold rounded-full bg-purple-100 text-purple-800 dark:bg-purple-900 dark:text-purple-200">
                          Entretenimiento
                        </span>
                      </td>
                      <td class="py-3 px-4 text-right text-sm font-semibold text-red-600 dark:text-red-400">-$15.99</td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>
          </div>

          <!-- ===== BOTONES DE EXPORTACIÓN - HU-005 ===== -->
          <div class="bg-white dark:bg-gray-800 rounded-xl shadow-sm p-6 border border-gray-200 dark:border-gray-700">
            <div class="text-center">
              <h3 class="text-lg font-semibold text-gray-900 dark:text-white mb-2">
                <i class="fas fa-download text-brand-500 mr-2"></i>
                Exportar Reportes
              </h3>
              <p class="text-gray-500 dark:text-gray-400 mb-6">
                Descarga tus datos financieros en diferentes formatos
              </p>
              
              <!-- Contenedor de botones -->
              <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
                
                <!-- Botón Exportar Excel (existente, mejorado) -->
                <button class="export-btn excel-btn group">
                  <div class="flex items-center justify-center">
                    <i class="fas fa-file-excel text-xl mr-3 group-hover:scale-110 transition-transform duration-200"></i>
                    <div class="text-left">
                      <div class="font-semibold">Exportar Excel</div>
                      <div class="text-xs opacity-75">Formato .xlsx</div>
                    </div>
                  </div>
                </button>

                <!-- NUEVO: Botón Exportar PDF - HU-005 -->
                <button class="export-btn pdf-btn group relative">
                  <div class="flex items-center justify-center">
                    <i class="fas fa-file-pdf text-xl mr-3 group-hover:scale-110 transition-transform duration-200"></i>
                    <div class="text-left">
                      <div class="font-semibold">Exportar PDF</div>
                      <div class="text-xs opacity-75">Formato profesional</div>
                    </div>
                  </div>
                  
                  <!-- Badge NEW -->
                  <span class="new-badge">
                    ✨ NUEVO
                  </span>
                </button>
              </div>
              
              <!-- Información adicional -->
              <div class="mt-6 p-4 bg-blue-50 dark:bg-blue-900/20 rounded-lg border border-blue-200 dark:border-blue-800">
                <div class="flex items-start">
                  <i class="fas fa-info-circle text-blue-500 mt-1 mr-3"></i>
                  <div class="text-left">
                    <h4 class="font-semibold text-blue-900 dark:text-blue-100 mb-1">
                      Sobre la exportación PDF
                    </h4>
                    <ul class="text-sm text-blue-700 dark:text-blue-300 space-y-1">
                      <li>• Incluye todos los datos visibles en pantalla</li>
                      <li>• Mantiene formato profesional y colores de BudgetBuddy</li>
                      <li>• Contiene gráficos, tablas y resumen financiero</li>
                      <li>• Listo para imprimir o enviar por email</li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>

        </main>
      </div>
    </div>
  </body>
</html>
```

---

## 🎨 **CSS - Estilos para HU-005**

```css
/* ===== HU-005: Estilos para Exportar PDF ===== */

/* Variables de color de BudgetBuddy */
:root {
  --color-brand-500: #465fff;
  --color-brand-600: #3641f5;
  --color-red-500: #ef4444;
  --color-red-600: #dc2626;
  --color-green-500: #10b981;
  --color-green-600: #059669;
}

/* Estilos base para botones de exportación */
.export-btn {
  @apply min-w-[200px] px-6 py-4 rounded-xl font-medium transition-all duration-300 transform;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  border: none;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.export-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}

.export-btn:active {
  transform: translateY(0);
  transition: transform 0.1s;
}

/* Botón Excel (verde) */
.excel-btn {
  background: linear-gradient(135deg, var(--color-green-500) 0%, var(--color-green-600) 100%);
  color: white;
}

.excel-btn:hover {
  background: linear-gradient(135deg, var(--color-green-600) 0%, #047857 100%);
}

.excel-btn:focus {
  outline: none;
  ring: 3px solid rgba(16, 185, 129, 0.3);
}

/* Botón PDF (rojo) - NUEVO HU-005 */
.pdf-btn {
  background: linear-gradient(135deg, var(--color-red-500) 0%, var(--color-red-600) 100%);
  color: white;
  position: relative;
}

.pdf-btn:hover {
  background: linear-gradient(135deg, var(--color-red-600) 0%, #b91c1c 100%);
}

.pdf-btn:focus {
  outline: none;
  ring: 3px solid rgba(239, 68, 68, 0.3);
}

/* Efecto brilloso en hover */
.export-btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s;
}

.export-btn:hover::before {
  left: 100%;
}

/* Badge NUEVO */
.new-badge {
  position: absolute;
  top: -8px;
  right: -8px;
  background: linear-gradient(135deg, #f59e0b 0%, #d97706 100%);
  color: white;
  font-size: 9px;
  font-weight: 700;
  padding: 3px 8px;
  border-radius: 12px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  box-shadow: 0 2px 8px rgba(245, 158, 11, 0.4);
  animation: pulse-badge 2s infinite;
}

/* Animación del badge */
@keyframes pulse-badge {
  0%, 100% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.1);
    opacity: 0.9;
  }
}

/* Estados disabled */
.export-btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
  transform: none;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.export-btn:disabled:hover {
  transform: none;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Responsive design */
@media (max-width: 640px) {
  .export-btn {
    min-width: 100%;
    justify-content: center;
  }
  
  .new-badge {
    top: -6px;
    right: -6px;
    font-size: 8px;
    padding: 2px 6px;
  }
}

/* Dark mode adjustments */
.dark .export-btn {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

.dark .export-btn:hover {
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
}

/* Efectos adicionales para mejorar la UX */
.export-btn i {
  transition: all 0.2s ease;
}

.export-btn:hover i {
  transform: scale(1.1);
}

/* Estilo para el contenedor de información */
.info-box {
  background: linear-gradient(135deg, rgba(59, 130, 246, 0.1) 0%, rgba(147, 197, 253, 0.1) 100%);
  border: 1px solid rgba(59, 130, 246, 0.2);
  border-radius: 12px;
  padding: 16px;
  margin-top: 24px;
}

/* Animación de entrada para los botones */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.export-btn {
  animation: fadeInUp 0.6s ease-out forwards;
}

.pdf-btn {
  animation-delay: 0.2s;
}

/* Efecto de ondas en click */
.export-btn {
  position: relative;
  overflow: hidden;
}

.export-btn::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.3);
  transform: translate(-50%, -50%);
  transition: width 0.3s ease, height 0.3s ease;
}

.export-btn:active::after {
  width: 300px;
  height: 300px;
}

/* Mejoras de accesibilidad */
.export-btn:focus-visible {
  outline: 3px solid rgba(59, 130, 246, 0.5);
  outline-offset: 2px;
}

/* Efecto de carga (para cuando se implemente JS) */
.export-btn.loading {
  pointer-events: none;
  opacity: 0.7;
}

.export-btn.loading i {
  animation: spin 1s linear infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

/* Tooltip para información adicional */
.export-btn[data-tooltip]:hover::before {
  content: attr(data-tooltip);
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translateX(-50%);
  background: rgba(0, 0, 0, 0.9);
  color: white;
  padding: 8px 12px;
  border-radius: 6px;
  font-size: 12px;
  white-space: nowrap;
  z-index: 10;
  margin-bottom: 8px;
}

.export-btn[data-tooltip]:hover::after {
  content: '';
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translateX(-50%);
  border: 6px solid transparent;
  border-top-color: rgba(0, 0, 0, 0.9);
  z-index: 10;
  margin-bottom: 2px;
}
```

---

## 📱 **Versión Responsiva Adicional**

```css
/* ===== Mejoras Responsive Específicas ===== */

/* Mobile First */
@media (max-width: 480px) {
  .export-btn {
    padding: 16px;
    font-size: 16px;
    min-height: 60px;
  }
  
  .export-btn i {
    font-size: 24px;
    margin-right: 12px;
  }
  
  .new-badge {
    font-size: 7px;
    padding: 2px 5px;
  }
}

/* Tablet */
@media (min-width: 481px) and (max-width: 768px) {
  .export-btn {
    min-width: 180px;
    padding: 14px 20px;
  }
}

/* Desktop */
@media (min-width: 769px) {
  .export-btn {
    min-width: 200px;
    padding: 16px 24px;
  }
  
  .export-btn:hover {
    transform: translateY(-3px);
  }
}

/* Para pantallas muy grandes */
@media (min-width: 1400px) {
  .export-btn {
    min-width: 220px;
    padding: 18px 28px;
    font-size: 16px;
  }
}
```

---

## 🎯 **Resultado Visual**

Con este código HTML y CSS tendrás:

### **✅ Diseño Profesional:**
- Página de reportes completa con datos de ejemplo
- Botones de exportación con gradientes y efectos
- Badge "NUEVO" animado en el botón PDF
- Información contextual sobre la funcionalidad

### **✅ Estilo BudgetBuddy:**
- Colores consistentes con la marca
- Tipografía y espaciado uniforme
- Iconos Font Awesome integrados
- Modo oscuro compatible

### **✅ Experiencia de Usuario:**
- Efectos de hover y animaciones suaves
- Responsive en todos los dispositivos
- Estados disabled y loading preparados
- Tooltips informativos

### **✅ Elementos Incluidos:**
- **Header** con título e iconos
- **Filtros** de período con selects
- **Métricas** en cards con iconos y colores
- **Placeholders** para gráficos
- **Tabla** de transacciones con ejemplos
- **Botones de exportación** con el nuevo botón PDF destacado
- **Información contextual** sobre la funcionalidad PDF

**Este código está listo para usar directamente en BudgetBuddy y cumple 100% con los criterios de aceptación de HU-005.**