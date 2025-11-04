# BudgetBuddy – Control de Gastos Personales

## Objetivo Principal

Proporcionar a los usuarios una herramienta web intuitiva y eficiente para gestionar sus finanzas personales, permitiéndoles tomar decisiones informadas sobre sus gastos e ingresos mediante el registro detallado de transacciones, visualización de reportes personalizados y acceso a asesoría financiera opcional, todo con el control total de su privacidad.

## Descripción General

BudgetBuddy es una aplicación web para el control de gastos personales, que permite a los usuarios registrar ingresos y egresos, organizarlos por categorías, y visualizar su balance de forma clara y accesible. Ofrece filtros por fecha, reportes personalizados y un resumen mensual del estado financiero.

Como valor agregado, los usuarios pueden marcar ciertas transacciones como públicas para recibir recomendaciones de un asesor. Este asesor solo podrá ver la información que el usuario decida compartir y podrá dar consejos generales sobre cómo mejorar su manejo financiero, sin acceder a datos privados ni sensibles.

## Recursos del Sistema (CRUD)

### 1. Transacciones
*Registro detallado acerca de cada ingreso o gasto*

- Crear transacciones (ingreso o gasto)
- Asignar categoría, monto, fecha, descripción
- Editar y eliminar transacciones
- Filtrar por fechas, categorías o tipo
- Visualización diaria/semanal/mensual

### 2. Categorías
*Clasificación para organizar las transacciones*

- Crear nuevas categorías personalizadas
- Editar o eliminar categorías existentes
- Ver totales agrupados por categoría
- Categorías base (alimentación, transporte, etc.) administradas por el sistema

### 3. Reportes
*Informes que resumen el estado financiero del usuario*

- Generar reportes semanales, mensuales o personalizados
- Mostrar total de ingresos, gastos, balance neto
- Progreso de metas de ahorro

### 4. Asesoría
*Funcionalidad para sugerencias financieras*

- Visualizar sólo las transacciones marcadas como públicas por el usuario
- Brindar sugerencias o consejos básicos sobre el manejo de finanzas, según los registros compartidos

## Roles y Permisos

Ya que se trata de una aplicación de finanzas personales, los datos serán privados, por lo que el Administrador no tendrá acceso directo a las finanzas de los usuarios.

| Rol | Permisos |
|-----|----------|
| **Usuario** | Crear, ver, actualizar y eliminar sus transacciones y categorías. También puede marcar ciertas transacciones como "públicas" para que puedan ser vistas por un asesor. |
| **Asesor** | Ver sólo las transacciones públicas de los usuarios. Puede dejar recomendaciones generales o consejos personalizados sobre el manejo de ingresos y egresos. |

## Tecnologías

- **Frontend:** Webpack
- **Backend:** Java (MVC) con Maven
- **Base de Datos:** PostgreSQL

## Deudas Técnicas

Funcionalidades pendientes de implementación o mejora:

### 1. Formato de Reportes en Excel
- **Problema:** Los reportes exportados a Excel no tienen un formato adecuado
- **Estado:** Pendiente de mejorar
- **Descripción:** La exportación de reportes genera archivos Excel con formato básico, sin estilos, columnas sin ajustar o estructura visual poco profesional

### 2. Sistema de Roles en Registro
- **Problema:** Falta implementar la selección de roles durante el registro de usuarios
- **Estado:** Pendiente de implementar
- **Descripción:** No existe un flujo completo para que los usuarios puedan registrarse como "Advisor" o "User" durante el proceso de sign-up. Actualmente no se puede diferenciar entre estos roles al momento del registro
