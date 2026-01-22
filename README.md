# 📊 ZAKIDATA Empowordato - Análisis de Personal con Power BI

<div align="center">

**Dashboard Interactivo para el Mapeo y Análisis de Empleados**

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Data Analysis](https://img.shields.io/badge/Análisis_de_Datos-Expert-0078D4?style=for-the-badge)](https://powerbi.microsoft.com/)
[![Business Intelligence](https://img.shields.io/badge/Business_Intelligence-Dashboard-FF6B6B?style=for-the-badge)](https://powerbi.microsoft.com/)
[![Licencia](https://img.shields.io/badge/Licencia-MIT-yellow?style=for-the-badge)](LICENSE)

[🚀 Características](#-características) • [📊 Instalación](#-instalación) • [🏗️ Arquitectura](#️-arquitectura) • [🎨 Diseño](#-diseño-del-dashboard) • [📈 Métricas](#-métricas-analizadas) • [👨‍💻 Autor](#-autor)

</div>

---

## 📊 Descripción del Proyecto

**ZAKIDATA Empowordato** es un dashboard interactivo desarrollado en **Power BI** que proporciona un análisis completo del personal de una organización. Este proyecto permite visualizar y analizar métricas clave de recursos humanos, como la distribución de empleados por edad, desempeño, años de contratación y salarios por departamento.

### 🎯 Objetivos del Proyecto
- Proporcionar una **visión general** de los empleados activos y su distribución.
- Analizar la **estructura demográfica** por rangos de edad.
- Evaluar el **desempeño de los empleados** y su clasificación.
- Mostrar la **evolución de contrataciones** a lo largo de los años.
- Comparar los **salarios promedio por departamento**.
- Facilitar la **toma de decisiones** en gestión de recursos humanos.

---

## 🚀 Características

### 📈 Métricas Principales
| Característica | Descripción | Estado |
|----------------|-------------|--------|
| **Empleados Activos** | Total de empleados activos y nómina total | ✅ Implementado |
| **Distribución por Edad** | Gráfico de barras por rangos de edad | ✅ Implementado |
| **Desempeño de Empleados** | Gráfico de barras con clasificación de desempeño | ✅ Implementado |
| **Año de Contratación** | Línea de tiempo de contrataciones por año | ✅ Implementado |
| **Salarios por Departamento** | Tabla con total de personal y salario promedio | ✅ Implementado |

### 🔍 Filtros e Interactividad
- **Filtros por departamento** para segmentar la información.
- **Interactividad entre gráficos** para un análisis detallado.
- **Tooltips informativos** al pasar el cursor sobre los datos.
- **Actualización automática** al conectarse a nuevas fuentes de datos.

---

## 📊 Instalación

### **Requisitos Previos**
1. **Power BI Desktop** (versión más reciente recomendada)
   - Descargar desde: [Microsoft Power BI](https://powerbi.microsoft.com/desktop/)
2. **Archivo de datos** (por ejemplo, Excel, CSV, SQL Server, etc.) con la estructura requerida.
3. **Permisos de acceso** a los datos si están en una base de datos o servicio en la nube.

### **Pasos de Instalación**
1. **Clonar el repositorio** (si está en GitHub) o descargar el archivo `.pbix`.
   ```bash
   git clone https://github.com/tu-usuario/zakidata-empowordato.git
   ```
2. **Abrir el archivo** `ZAKIDATA_Empowordato.pbix` con Power BI Desktop.
3. **Configurar la fuente de datos** si es necesario:
   - Ir a "Inicio" > "Transformar datos" > "Configuración de origen de datos".
   - Actualizar la ruta o conexión a tu archivo de datos.
4. **Actualizar los datos** (si se han cambiado):
   - Hacer clic en "Actualizar" en la pestaña "Inicio".
5. **Explorar el dashboard** interactuando con los gráficos y filtros.

### **Estructura de Datos Requerida**
El dashboard espera una tabla con al menos las siguientes columnas:
- `ID_Empleado`
- `Nombre`
- `Edad` (o fecha de nacimiento)
- `Departamento`
- `Salario`
- `Fecha_Contratacion`
- `Desempeño` (categorías: "Dentro de lo esperado", "Por debajo", "Por encima", etc.)

---

## 🏗️ Arquitectura

### **Flujo de Datos**
```
Fuente de Datos (Excel/CSV/SQL) → Power BI Query Editor → Modelo de Datos → Visualizaciones → Dashboard
```

### **Modelo de Datos**
El modelo de datos consta de una tabla principal `Empleados` que puede estar relacionada con tablas de dimensiones como `Departamentos`, `Fechas`, etc.

### **Estructura del Proyecto**
```
ZAKIDATA_Empowordato/
├── data/                    # Archivos de datos (no incluidos por privacidad)
│   └── empleados.csv       # Datos de ejemplo
├── docs/                   # Documentación adicional
│   └── especificaciones.md
├── images/                 # Capturas de pantalla
│   └── dashboard.png
├── ZAKIDATA_Empowordato.pbix   # Archivo principal de Power BI
└── README.md               # Este archivo
```

### **Medidas y Columnas Calculadas**
Se utilizan medidas DAX para calcular métricas como:
- **Total Empleados**: `Total_Empleados = COUNTROWS(Empleados)`
- **Salario Total**: `Salario_Total = SUM(Empleados[Salario])`
- **Salario Promedio por Departamento**: `Promedio_Salario = AVERAGE(Empleados[Salario])`
- **Distribución por Edad**: Se crea una columna calculada para agrupar las edades en rangos.

---

## 🎨 Diseño del Dashboard

### **Tema y Colores**
- **Tema oscuro** para un contraste óptimo y reducir la fatiga visual.
- **Paleta de colores corporativa** (azul, gris, naranja) para mantener la identidad de marca.
- **Tipografía clara y legible** (Segoe UI por defecto).

### **Layout y Organización**
El dashboard está organizado en secciones lógicas:
1. **Encabezado**: Título del proyecto y logo.
2. **Métricas clave**: Tarjetas con números importantes (empleados activos, salario total).
3. **Distribución por edad**: Gráfico de barras horizontales.
4. **Desempeño**: Gráfico de barras verticales.
5. **Contrataciones por año**: Gráfico de líneas.
6. **Tabla de departamentos**: Tabla con totales y promedios.

### **Interactividad**
- **Segmentación de datos** por departamento y rango de edad.
- **Cruce de filtros**: Al hacer clic en un rango de edad, se filtran automáticamente los demás gráficos.
- **Tooltips personalizados** que muestran información adicional.

---

## 📈 Métricas Analizadas

### **1. Empleados Activos**
- **Total**: 207 empleados.
- **Salario total**: $1,392,870.00.

### **2. Distribución por Edad**
- Mayor concentración en el rango de **26-30 años** (55 empleados).
- Seguido por **31-35 años** (46 empleados) y **36-40 años** (44 empleados).
- Menos empleados en los rangos extremos (21-25 y 51-55).

### **3. Desempeño de Empleados**
- **Dentro de lo esperado**: 162 empleados.
- **Por encima de lo esperado**: 29 empleados.
- **Por debajo de lo esperado**: 16 empleados.

### **4. Año de Contratación**
- La contratación ha ido aumentando con los años, con un pico en **2018** (19 contrataciones).
- Los datos van desde 2010 hasta 2018.

### **5. Departamento y Salarios**
| Departamento    | Total Personal | Salario Promedio |
|-----------------|----------------|------------------|
| Administrativo  | 8              | $8,304           |
| Producción      | 125            | $5,164           |
| TI              | 47             | $9,909           |
| Ventas          | 27             | $7,970           |
| **Total**       | **207**        | **$6,729**       |

- **TI** tiene el salario promedio más alto ($9,909), mientras que **Producción** tiene el más bajo ($5,164).

---

## 👨‍💻 Autor

<div align="center">

**Darwin Manuel Ovalles Cesar**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Perfil_Profesional-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/darwin-manuel-ovalles-cesar-dev/)
[![GitHub](https://img.shields.io/badge/GitHub-Repositorios-black?style=flat&logo=github)](https://github.com/dovalless)

💼 **Analista de Datos & Business Intelligence**  
🎓 **Especialista en Power BI y Visualización de Datos**  
📊 **Apasionado por la toma de decisiones basada en datos**

*"Este dashboard de Power BI permite transformar datos brutos de recursos humanos en información valiosa para la gestión estratégica del personal. Cada gráfico y métrica está diseñada para responder preguntas clave sobre la fuerza laboral."*

**#PowerBI #DataAnalysis #BusinessIntelligence #HRanalytics #Dashboard**

</div>

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.

```
MIT License
Copyright (c) 2024 Darwin Manuel Ovalles Cesar
```

---

<div align="center">

### ⭐ Si este proyecto te resulta útil, ¡dale una estrella en GitHub! ⭐

### 📈 Convierte tus datos en decisiones inteligentes con Power BI 📈

**Desarrollado con ❤️ y 📊 para impulsar la toma de decisiones basada en datos**

---
*Dashboard de análisis de personal | Business Intelligence | Recursos Humanos*

</div>
