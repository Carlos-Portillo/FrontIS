# Propuesta de Modificaciones - BudgetBuddy

## 3. Definición de Modificaciones y Asignación de Tareas

### Duración Estimada: 2 semanas (Sprint)

---

## 📋 Lista de Modificaciones Propuestas

### **Módulo 1: Sistema de Roles y Autenticación** ⭐ (DEUDA TÉCNICA)
**Responsable:** [Integrante 1]  
**Estimación:** 3-4 días  
**Tipo:** Frontend + Backend (Validación)

#### Tareas:
1. **Implementar sistema de validación de rol en Sign Up**
   - Ocultar opción de ADVISOR por defecto (solo mostrar USER)
   - Agregar componente de "Código de Asesor" con validación frontend
   - Crear lista de códigos válidos hardcodeados en frontend
   - Implementar lógica para habilitar opción ADVISOR al validar código correcto
   - Agregar validación dentro del registro frontend para roles USER/ADVISOR
   - Conectar selector de roles con el backend
   - Validar que el rol se guarde correctamente en la BD
   - Agregar indicadores visuales según el rol seleccionado y estado de validación

2. **Crear diferenciación de roles en el sistema**
   - Implementar lógica de permisos según rol
   - Restringir acceso a funcionalidades específicas por rol (ej: Advisors ven transacciones públicas)
   - Mostrar/ocultar opciones del menú según el rol del usuario
   - Agregar badges o indicadores visuales del rol en la interfaz

3. **Pruebas y validación**
   - Verificar flujo completo de registro con ambos roles
   - Probar validación de código de asesor (códigos válidos e inválidos)
   - Validar persistencia del rol después de login/logout
   - Verificar restricciones de acceso según rol

---

### **Módulo 2: Mejora de Exportación de Reportes** ⭐ (DEUDA TÉCNICA)
**Responsable:** [Integrante 2]  
**Estimación:** 3-4 días  
**Tipo:** Frontend (100%)

#### Tareas:
1. **Implementar exportación a Excel con formato profesional**
   - Integrar librería de exportación (xlsx, exceljs o similar)
   - Diseñar plantilla con estilos y formato corporativo
   - Agregar encabezados, colores, bordes y formatos de celdas
   - Incluir gráficos/resumen visual en la hoja de Excel

2. **Agregar múltiples formatos de exportación**
   - Implementar exportación a PDF
   - Crear botones para cada formato de exportación

3. **Validación y pruebas**
   - Verificar que los datos sean correctos en las exportaciones
   - Probar en diferentes navegadores

---

### **Módulo 3: Mejoras en Página de Perfil de Usuario**
**Responsable:** [Integrante 3]  
**Estimación:** 2-3 días  
**Tipo:** Frontend (usando datos existentes o localStorage)

#### Tareas:
1. **Ampliar información del perfil**
   - Agregar campos editables para el perfil (usando localStorage o campos existentes del backend)
   - Implementar campo de biografía/descripción personal
   - Mostrar rol del usuario en el perfil

2. **Implementar edición de información personal**
   - Crear modal o formulario inline para editar datos
   - Validar campos antes de guardar
   - Mostrar notificaciones de éxito/error

---

### **Módulo 4: Panel de Estadísticas y Dashboard Mejorado**
**Responsable:** [Integrante 4]  
**Estimación:** 3-4 días  
**Tipo:** Frontend (100% - Cálculos con datos existentes)

#### Tareas:
1. **Agregar nuevos gráficos y métricas**
   - Gráfico de tendencia de gastos (últimos 6 meses)
   - Gráfico de distribución por categorías (pie chart)
   - Indicador de gasto promedio diario/semanal
   - Usar datos de transacciones existentes para los cálculos

---

### **Módulo 5: Filtros Avanzados y Búsqueda en Transacciones**
**Responsable:** [Integrante 5]  
**Estimación:** 2-3 días  
**Tipo:** Frontend (100% - Filtrado en memoria)

#### Tareas:
1. **Implementar filtros múltiples simultáneos**
   - Filtro por rango de fechas con calendario
   - Filtro por rango de montos (desde/hasta)
   - Filtro por múltiples categorías a la vez
   - Todos los filtros se aplican sobre datos cargados en memoria

2. **Agregar buscador de transacciones**
   - Búsqueda por descripción (texto libre)
   - Búsqueda en tiempo real (autocompletado)
   - Resaltado de resultados

3. **Implementar ordenamiento flexible**
   - Ordenar por fecha, monto, categoría, tipo
   - Orden ascendente/descendente
   - Guardar preferencias de ordenamiento en localStorage

---

### **Módulo 6: Panel de Asesoría Financiera Mejorado** 🎓
**Responsable:** [Integrante 6]  
**Estimación:** 3-4 días  
**Tipo:** Frontend (100%)

#### Tareas:
1. **Ampliar Dashboard de Advisor**
   - Crear vista de resumen con métricas de asesorías realizadas
   - Mostrar lista de usuarios que tienen transacciones públicas disponibles
   - Implementar contador de asesorías dadas por advisor
   - Agregar filtros para ver asesorías por fecha o usuario

2. **Mejorar sistema de asesorías**
   - Crear modal/formulario mejorado para dar asesorías
   - Agregar categorización de asesorías (ahorro, reducción de gastos, inversión, etc.)
   - Implementar vista de transacciones públicas del usuario con gráficos
   - Permitir al advisor ver histórico de asesorías dadas a cada usuario

3. **Panel de análisis para Advisor**
   - Mostrar gráfico de distribución de gastos del usuario
   - Calcular y mostrar métricas útiles (promedio de gasto, categoría más alta, etc.)
   - Sugerencias automáticas basadas en patrones (ej: "Usuario gasta 40% en entretenimiento")
   - Timeline de transacciones públicas para ver tendencias

4. **Mejoras en UI/UX del módulo Advisor**
   - Implementar estados de carga (loading) en carga de transacciones públicas
   - Agregar tooltips explicativos sobre responsabilidades del advisor
   - Mejorar responsividad móvil del panel de advisor
   - Notificaciones cuando nuevos usuarios marcan transacciones como públicas

---

## 📊 Resumen de Distribución de Trabajo

| Integrante | Módulo | Complejidad | Días Estimados |
|------------|--------|-------------|----------------|
| Integrante 1 | Sistema de Roles | Alta | 3-4 |
| Integrante 2 | Exportación Reportes | Media-Alta | 3-4 |
| Integrante 3 | Perfil de Usuario | Media | 2-3 |
| Integrante 4 | Dashboard/Estadísticas | Alta | 3-4 |
| Integrante 5 | Filtros Avanzados | Media | 2-3 |
| Integrante 6 | Panel de Asesoría | Alta | 3-4 |

---

## 🎯 Objetivos por Semana

### **Semana 1: Funcionalidades Core**
- ✅ Módulo 1: Sistema de Roles (Completo)
- ✅ Módulo 2: Exportación de Reportes (80%)
- ✅ Módulo 3: Perfil de Usuario (Completo)
- 🔄 Módulo 4: Dashboard Usuario (60%)
- 🔄 Módulo 5: Filtros (50%)
- 🔄 Módulo 6: Panel Advisor (50%)

### **Semana 2: Refinamiento y Pruebas**
- ✅ Finalizar Módulo 2: Exportación (100%)
- ✅ Finalizar Módulo 4: Dashboard Usuario (100%)
- ✅ Finalizar Módulo 5: Filtros (100%)
- ✅ Finalizar Módulo 6: Panel Advisor (100%)
- 🧪 Pruebas integradas de todos los módulos
- 🧪 Pruebas específicas de interacción User-Advisor
- 📝 Documentación de cambios y nuevas features
- 🐛 Corrección de bugs identificados
- 🎨 Pulido final de interfaz

---

## 🔧 Tecnologías y Herramientas Adicionales

### Librerías Nuevas a Integrar (Frontend):
1. **ExcelJS** o **SheetJS (xlsx)** - Para exportación mejorada de Excel
2. **jsPDF** - Para exportación a PDF
3. **Chart.js** (ya existente) - Para nuevos gráficos y métricas
4. **date-fns** o **dayjs** (opcional) - Para manejo avanzado de fechas en filtros

### Backend:
- **Mínimas modificaciones requeridas:** Solo validación del sistema de roles (Módulo 1)
- **Resto de módulos:** 100% frontend, no requieren cambios en el backend

---

## 📈 Métricas de Éxito

1. **Funcionalidad Completa:**
   - ✅ 100% de las deudas técnicas resueltas
   - ✅ 6 módulos nuevos implementados completamente
   - ✅ Módulo de Advisor significativamente mejorado (de simple historial a panel completo)

2. **Calidad de Código:**
   - ✅ Código documentado
   - ✅ Seguimiento de estándares del proyecto
   - ✅ Sin errores críticos en consola

3. **Experiencia de Usuario:**
   - ✅ Tiempos de carga reducidos
   - ✅ Interfaz más intuitiva y profesional
   - ✅ Feedback visual en todas las acciones
   - ✅ Panel de Advisor funcional y útil para asesores

4. **Pruebas:**
   - ✅ Cada módulo probado individualmente
   - ✅ Pruebas de integración completas
   - ✅ Validación en diferentes navegadores
   - ✅ Pruebas de interacción User-Advisor

---

## 📝 Notas Importantes

- Cada integrante debe crear **historias de usuario** específicas para sus tareas antes de comenzar
- Se deben realizar **commits frecuentes** con mensajes descriptivos
- **Daily stand-ups** de 10 minutos para sincronizar avances
- Uso de **ramas feature/** para cada módulo
- **Code review** antes de merge a main
- Documentar cualquier decisión técnica importante

---

## 🚀 Plan de Implementación

### Metodología:
- **Scrum/Agile** con sprints de 1 semana
- **Jira** para seguimiento de tareas
- **Git Flow** para manejo de ramas
- **Pull Requests** obligatorios con revisión

### Definición de "Done":
- ✅ Código funcional y testeado
- ✅ Sin errores en consola
- ✅ Responsivo en móvil y desktop
- ✅ Documentación básica agregada
- ✅ Revisado y aprobado por al menos 1 compañero
- ✅ Merged a rama main

---

## 📞 Puntos de Sincronización

1. **Kick-off Meeting** - Día 1 (1 hora)
   - Asignación final de módulos
   - Revisión de dependencias entre módulos
   - Setup de ambiente de desarrollo

2. **Mid-Sprint Review** - Día 4 (30 min)
   - Revisión de avances
   - Identificación de blockers
   - Ajuste de estimaciones si necesario

3. **Sprint Review** - Día 7 (1 hora)
   - Demo de funcionalidades completadas
   - Feedback del equipo
   - Planificación semana 2

4. **Final Demo** - Día 14 (1 hora)
   - Presentación completa del proyecto
   - Validación de todos los módulos
   - Entrega formal

---

## ✅ Checklist Pre-Entrega

- [ ] Todas las deudas técnicas resueltas
- [ ] Código en repositorio actualizado
- [ ] README.md actualizado con nuevas funcionalidades
- [ ] Board de Jira con todas las tareas completadas
- [ ] Documentación de API actualizada (si aplica)
- [ ] Video demo de 3-5 minutos mostrando cambios
- [ ] Presentación PowerPoint para defensa final
