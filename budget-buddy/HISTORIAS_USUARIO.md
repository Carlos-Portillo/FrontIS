# Historias de Usuario - BudgetBuddy

## Módulo 1: Sistema de Roles y Autenticación

### HU-001: Registro como Usuario Regular
**Como** un nuevo usuario  
**Quiero** registrarme en la aplicación seleccionando el rol de Usuario  
**Para** poder gestionar mis finanzas personales

**Criterios de Aceptación:**
- El formulario de registro muestra la opción "Usuario" visible por defecto
- La opción "Asesor Financiero" está oculta inicialmente
- Al completar el registro, el usuario es creado con el rol USER
- El rol se persiste correctamente en la base de datos
- Después del login, el usuario puede acceder a todas las funcionalidades de usuario regular

**Prioridad:** Alta  
**Estimación:** 1 día

---

### HU-002: Registro como Asesor Financiero con Código de Validación
**Como** un asesor financiero  
**Quiero** registrarme utilizando un código de validación  
**Para** obtener acceso a funcionalidades exclusivas de asesoramiento

**Criterios de Aceptación:**
- Existe un campo para ingresar "Código de Asesor" en el formulario de registro
- Al ingresar un código válido, se habilita la opción de rol "Asesor Financiero"
- Al ingresar un código inválido, se muestra un mensaje de error claro
- Solo con código válido se puede seleccionar el rol ADVISOR
- El rol ADVISOR se guarda correctamente en la base de datos
- Se muestran indicadores visuales del estado de validación del código

**Prioridad:** Alta  
**Estimación:** 2 días

---

### HU-003: Diferenciación de Permisos por Rol
**Como** usuario del sistema  
**Quiero** que mi interfaz y permisos se ajusten según mi rol  
**Para** tener acceso solo a las funcionalidades relevantes para mí

**Criterios de Aceptación:**
- Los usuarios con rol USER solo ven opciones de gestión personal
- Los usuarios con rol ADVISOR ven opciones adicionales de asesoría
- El menú lateral muestra/oculta opciones según el rol
- Se muestran badges o indicadores visuales del rol en la interfaz
- Los permisos se validan correctamente después de login/logout
- No es posible acceder a funcionalidades restringidas manipulando la URL

**Prioridad:** Alta  
**Estimación:** 1 día

---

## Módulo 2: Mejora de Exportación de Reportes

### HU-004: Exportar Reporte a Excel con Formato Profesional
**Como** usuario  
**Quiero** exportar mis reportes financieros a Excel con formato profesional  
**Para** poder compartirlos y presentarlos de manera clara y organizada

**Criterios de Aceptación:**
- Existe un botón "Exportar a Excel" claramente visible en la página de reportes
- El archivo Excel generado incluye encabezados con estilos (colores, negritas)
- Las celdas tienen bordes y formato apropiado
- Los números están formateados como moneda
- El archivo incluye un resumen visual o gráfico
- El nombre del archivo incluye la fecha de generación
- La exportación funciona en Chrome, Firefox y Safari

**Prioridad:** Alta  
**Estimación:** 2 días

---

### HU-005: Exportar Reporte a PDF
**Como** usuario  
**Quiero** exportar mis reportes a formato PDF  
**Para** tener una versión lista para imprimir o enviar por email

**Criterios de Aceptación:**
- Existe un botón "Exportar a PDF" en la página de reportes
- El PDF generado mantiene el formato y diseño visual del reporte
- Incluye todos los datos visibles en pantalla
- El PDF es legible y tiene buena calidad
- El archivo se descarga automáticamente con nombre descriptivo

**Prioridad:** Media  
**Estimación:** 1-2 días

---

## Módulo 3: Mejoras en Página de Perfil de Usuario

### HU-006: Ampliar Información del Perfil
**Como** usuario  
**Quiero** agregar más información a mi perfil personal  
**Para** personalizar mi experiencia en la aplicación

**Criterios de Aceptación:**
- Puedo agregar una biografía o descripción personal
- Se muestra mi rol (Usuario o Asesor) en el perfil
- Puedo ver todos los campos de mi perfil en una vista organizada
- La información se guarda en localStorage o en el backend
- Los cambios persisten después de cerrar sesión

**Prioridad:** Media  
**Estimación:** 1 día

---

### HU-007: Editar Información Personal
**Como** usuario  
**Quiero** editar mi información personal desde mi perfil  
**Para** mantener mis datos actualizados

**Criterios de Aceptación:**
- Existe un botón "Editar Perfil" claramente visible
- Al hacer clic se muestra un modal o formulario inline editable
- Puedo modificar campos como nombre, email, biografía
- Los campos tienen validación antes de guardar
- Se muestra un mensaje de éxito al guardar correctamente
- Se muestra un mensaje de error si algo falla
- Puedo cancelar la edición sin guardar cambios

**Prioridad:** Media  
**Estimación:** 1-2 días

---

## Módulo 4: Panel de Estadísticas y Dashboard Mejorado

### HU-008: Ver Gráfico de Tendencia de Gastos
**Como** usuario  
**Quiero** ver un gráfico de tendencia de mis gastos de los últimos 6 meses  
**Para** identificar patrones en mi comportamiento financiero

**Criterios de Aceptación:**
- El dashboard muestra un gráfico de línea con gastos mensuales
- El gráfico incluye los últimos 6 meses
- Los datos se calculan automáticamente desde mis transacciones
- El gráfico es interactivo (hover muestra valores exactos)
- Se actualiza automáticamente al agregar nuevas transacciones

**Prioridad:** Alta  
**Estimación:** 1-2 días

---

### HU-009: Ver Distribución de Gastos por Categoría
**Como** usuario  
**Quiero** ver un gráfico circular de distribución de gastos por categoría  
**Para** entender en qué estoy gastando más dinero

**Criterios de Aceptación:**
- El dashboard muestra un gráfico circular (pie chart) con categorías
- Cada categoría tiene un color distintivo
- Se muestra el porcentaje de cada categoría
- Al hacer hover se muestra el monto exacto
- Solo se incluyen las categorías con gastos en el período seleccionado

**Prioridad:** Alta  
**Estimación:** 1 día

---

### HU-010: Ver Indicadores de Gasto Promedio
**Como** usuario  
**Quiero** ver mi gasto promedio diario y semanal  
**Para** tener una referencia rápida de mis hábitos de consumo

**Criterios de Aceptación:**
- El dashboard muestra un card con "Gasto Promedio Diario"
- Se muestra otro card con "Gasto Promedio Semanal"
- Los cálculos se basan en transacciones del último mes
- Los valores se actualizan automáticamente
- Se muestran con formato de moneda

**Prioridad:** Media  
**Estimación:** 1 día

---

## Módulo 5: Filtros Avanzados y Búsqueda en Transacciones

### HU-011: Filtrar Transacciones por Múltiples Criterios
**Como** usuario  
**Quiero** aplicar múltiples filtros simultáneamente a mis transacciones  
**Para** encontrar rápidamente las transacciones que necesito revisar

**Criterios de Aceptación:**
- Puedo filtrar por rango de fechas usando un selector de calendario
- Puedo filtrar por rango de montos (desde/hasta)
- Puedo seleccionar múltiples categorías a la vez
- Todos los filtros se aplican simultáneamente
- La tabla se actualiza en tiempo real al cambiar filtros
- Existe un botón para limpiar todos los filtros

**Prioridad:** Alta  
**Estimación:** 2 días

---

### HU-012: Buscar Transacciones por Descripción
**Como** usuario  
**Quiero** buscar transacciones por descripción o palabra clave  
**Para** encontrar rápidamente transacciones específicas

**Criterios de Aceptación:**
- Existe un campo de búsqueda visible en la página de transacciones
- La búsqueda funciona en tiempo real mientras escribo
- Se busca en el campo de descripción de las transacciones
- Los resultados se filtran instantáneamente
- Se resaltan las coincidencias en los resultados

**Prioridad:** Media  
**Estimación:** 1 día

---

### HU-013: Ordenar Transacciones Flexiblemente
**Como** usuario  
**Quiero** ordenar mis transacciones por diferentes criterios  
**Para** analizar mis datos desde diferentes perspectivas

**Criterios de Aceptación:**
- Puedo ordenar por fecha, monto, categoría o tipo
- Puedo alternar entre orden ascendente y descendente
- El orden se aplica inmediatamente al hacer clic en el encabezado
- Se muestra un indicador visual del criterio de ordenamiento actual
- La preferencia de ordenamiento se guarda en localStorage

**Prioridad:** Media  
**Estimación:** 1 día

---

## Módulo 6: Panel de Asesoría Financiera Mejorado

### HU-014: Ver Dashboard de Asesor con Métricas
**Como** asesor financiero  
**Quiero** ver un dashboard con métricas de mis asesorías  
**Para** hacer seguimiento de mi trabajo y rendimiento

**Criterios de Aceptación:**
- El dashboard muestra número total de asesorías realizadas
- Se muestra lista de usuarios con transacciones públicas disponibles
- Existe un contador de asesorías por período
- Puedo filtrar asesorías por fecha
- Puedo ver qué usuarios he asesorado
- Las métricas se actualizan automáticamente

**Prioridad:** Alta  
**Estimación:** 1-2 días

---

### HU-015: Crear Asesoría Categorizada
**Como** asesor financiero  
**Quiero** crear asesorías con categorías específicas  
**Para** organizar mejor mis recomendaciones a los usuarios

**Criterios de Aceptación:**
- Existe un modal mejorado para crear asesorías
- Puedo seleccionar categoría (ahorro, reducción de gastos, inversión, etc.)
- Puedo escribir el contenido de la asesoría
- Puedo ver las transacciones públicas del usuario antes de asesorar
- La asesoría se guarda con la categoría seleccionada
- Se muestra confirmación al guardar exitosamente

**Prioridad:** Alta  
**Estimación:** 2 días

---

### HU-016: Analizar Transacciones Públicas de Usuario
**Como** asesor financiero  
**Quiero** ver análisis detallado de las transacciones públicas de un usuario  
**Para** proporcionar asesorías más precisas y útiles

**Criterios de Aceptación:**
- Puedo ver gráfico de distribución de gastos del usuario
- Se muestran métricas calculadas (promedio, categoría más alta, etc.)
- Veo sugerencias automáticas basadas en patrones
- Puedo ver timeline de transacciones para identificar tendencias
- Toda la información se carga sin errores
- Se muestran estados de carga mientras se procesan los datos

**Prioridad:** Alta  
**Estimación:** 2 días

---

### HU-017: Ver Histórico de Asesorías por Usuario
**Como** asesor financiero  
**Quiero** ver el histórico de asesorías que he dado a cada usuario  
**Para** dar seguimiento y evitar repetir consejos

**Criterios de Aceptación:**
- Puedo seleccionar un usuario y ver todas mis asesorías anteriores
- Las asesorías se muestran ordenadas por fecha
- Cada asesoría muestra su categoría y contenido
- Puedo filtrar asesorías por categoría
- El histórico es fácil de navegar

**Prioridad:** Media  
**Estimación:** 1 día

---

### HU-018: Recibir Notificación de Nuevas Transacciones Públicas
**Como** asesor financiero  
**Quiero** recibir notificaciones cuando usuarios marquen transacciones como públicas  
**Para** estar al tanto de nuevas oportunidades de asesoría

**Criterios de Aceptación:**
- Se muestra una notificación visual cuando hay nuevas transacciones públicas
- La notificación indica cuántos usuarios nuevos hay
- Puedo hacer clic en la notificación para ir directamente al panel de asesorías
- Las notificaciones se marcan como leídas al revisarlas
- Se usa badge o contador en el menú del módulo de asesorías

**Prioridad:** Baja  
**Estimación:** 1 día

---

## Historias de Usuario Transversales

### HU-019: Experiencia Responsive en Dispositivos Móviles
**Como** usuario  
**Quiero** que todas las nuevas funcionalidades sean accesibles desde mi móvil  
**Para** gestionar mis finanzas desde cualquier dispositivo

**Criterios de Aceptación:**
- Todos los nuevos módulos son responsive
- Los gráficos se adaptan correctamente a pantallas pequeñas
- Los modales y formularios son usables en móvil
- No hay scroll horizontal innecesario
- Los botones tienen tamaño adecuado para tocar con el dedo

**Prioridad:** Alta  
**Estimación:** Transversal a todos los módulos

---

### HU-020: Feedback Visual en Todas las Acciones
**Como** usuario  
**Quiero** recibir feedback visual inmediato en todas mis acciones  
**Para** saber que el sistema está procesando mi solicitud

**Criterios de Aceptación:**
- Todas las acciones muestran estados de carga (spinners, skeletons)
- Los botones se deshabilitan mientras se procesa una acción
- Se muestran mensajes de éxito al completar operaciones
- Se muestran mensajes de error claros cuando algo falla
- Las notificaciones se auto-ocultan después de unos segundos

**Prioridad:** Media  
**Estimación:** Transversal a todos los módulos

---

## Resumen por Prioridad

### Prioridad Alta (11 historias):
- HU-001, HU-002, HU-003, HU-004, HU-008, HU-009, HU-011, HU-014, HU-015, HU-016, HU-019

### Prioridad Media (7 historias):
- HU-005, HU-006, HU-007, HU-010, HU-012, HU-013, HU-017, HU-020

### Prioridad Baja (1 historia):
- HU-018

---

## Resumen por Módulo

| Módulo | Historias | Total Estimado |
|--------|-----------|----------------|
| Módulo 1 | HU-001, HU-002, HU-003 | 4 días |
| Módulo 2 | HU-004, HU-005 | 3-4 días |
| Módulo 3 | HU-006, HU-007 | 2-3 días |
| Módulo 4 | HU-008, HU-009, HU-010 | 3-4 días |
| Módulo 5 | HU-011, HU-012, HU-013 | 4 días |
| Módulo 6 | HU-014, HU-015, HU-016, HU-017, HU-018 | 7-8 días |
| Transversal | HU-019, HU-020 | Distribuido |

---

## Notas de Implementación

### Dependencias entre Historias:
- HU-002 depende de HU-001 (sistema base de registro)
- HU-003 depende de HU-001 y HU-002 (roles implementados)
- HU-015 y HU-016 dependen de HU-014 (dashboard base de advisor)
- HU-017 depende de HU-015 (asesorías creadas)

### Criterios de Aceptación Generales:
Todas las historias deben cumplir con:
- ✅ Código funcional sin errores en consola
- ✅ Validación de datos de entrada
- ✅ Mensajes de error claros y amigables
- ✅ Diseño consistente con el resto de la aplicación
- ✅ Pruebas manuales completadas
- ✅ Code review aprobado

---

## Definición de "Listo" (Definition of Ready)

Una historia está lista para implementarse cuando:
- ✅ Tiene criterios de aceptación claros y medibles
- ✅ El equipo entiende completamente los requerimientos
- ✅ Se han identificado las dependencias técnicas
- ✅ Está estimada en puntos de historia o días
- ✅ Tiene prioridad asignada

---

## Definición de "Hecho" (Definition of Done)

Una historia está completa cuando:
- ✅ Todos los criterios de aceptación están cumplidos
- ✅ El código está revisado y aprobado
- ✅ No hay errores críticos en consola
- ✅ Funciona en diferentes navegadores
- ✅ Es responsive (mobile y desktop)
- ✅ Tiene manejo de errores apropiado
- ✅ Está documentado si es necesario
- ✅ Está integrado en la rama principal
