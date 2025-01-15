# DRIS V3.3.4 (Dataware Report Integrated System)

<center>

![](/assets/images/DatawareOKnegro.png)

</center>

<center>

[![Dataware](https://img.shields.io/badge/-Dataware-yellow)](https://www.dataware.com.mx/)
[![ST](https://img.shields.io/badge/-Soporte%20T%C3%A9cnico-orange)](https://www.dataware.com.mx/soporte-tecnico)
[![Android app](https://img.shields.io/badge/Android-App-green)](https://developer.android.com/?hl=es-419)
[![SIT](https://img.shields.io/badge/SIT-Dev-blue?style=plastic&logo=SIT&logoColor=blue)](https://www.dataware.com.mx/servicios-profesionales)



</center>

---

## Sobre este proyecto

El departamento de **Servicios de Integración Tecnológica** recibió la solicitud de rediseñar la aplicación de **CAPTURA DE REPORTES** utilizando **Android Studio** en lugar de **Kalipso**. El objetivo del rediseño es lograr una mayor robustez y mejorar la experiencia del usuario. La nueva aplicación, **DRIS**, conserva un diseño basado en la aplicación anterior pero incluye nuevas funciones.
## Tecnologías

![java](https://img.shields.io/badge/Java-red?style=for-the-badge&logo=Android%20Studio&logoColor=white&labelColor=black)
![Gradle](https://img.shields.io/badge/Gradle-purple?style=for-the-badge&logo=Gradle&logoColor=white&labelColor=black)
![Zebra](https://img.shields.io/badge/Zebra-grey?style=for-the-badge&logo=zebratechnologies&logoColor=white&labelColor=black)


### Objetivo
Crear una aplicación en **Android Studio** que agilice la generación de reportes de mantenimiento y servicio, con el fin de optimizar y eficientar el trabajo de los técnicos de Soporte Técnico y mejorar la experiencia del cliente.

### ¿Para qué sirve DRIS?
- Se han implementado varias interfaces que permiten al usuario generar reportes específicos según el cliente atendido. Actualmente, se pueden generar reportes de mantenimiento para Bocar, Mercado Libre y Otros Clientes, así como reportes de servicio para cualquier tipo de cliente en el formato Dataware.
- Conteo de registros
- Vista previa a registros
- Mayor espacio en comentarios
- Reportes específicos dependiendo del cliente
  - Reporte Excel
  - Reporte PDF
  - Reporte de Servicio por número de serie
- Evíar reporte por correo electrónico
- Editar firmas antes de crear PDF
- Cambiar Cliente
- Crear Bases de Datos
- Borrar Bases de Datos
- Borrar registros individuales

---
## App
Para instalar el [apk](/assets/apk/DRIS%203.3.1.apk) en tu dispositivo sigue el [Manual de Ususario](/assets/PDF/Presentación%20Reportes_ST.pdf) o clona el repositorio desde **Github** y carga la app desde **Android Studio**. **La aplicación esta probada en A10, A11, A12 y A13.**

```bash
git clone https://github.com/EsCumDW/DRIS-Dataware-Report-Integrated-System.git
```

## Otros Clientes

En la Actividad de **Otros Clientes** se capturan datos como: 

- Modelo
- Numero de Serie
- Cambio de refacciones
    - Banda
    - Rodillo
    - Cabezal
    - Sensor
- Pulgadas del encoder
- Comentarios

Esta sección permite la inclusión de múltiples registros en diversas bases de datos según sea necesario. El documento es firmado por ambas partes: el responsable de Dataware Soluciones y el responsable del cliente actual. Además, se registran el asunto del reporte, el tipo de llamada y el número de ticket.

Como resultado de esta actividad, se adjuntan un archivo al correo electrónico: **un reporte en formato PDF**.

---
## Bocar

En la Actividad de **Bocar** se capturan datos como: 

- Modelo
- Numero de Serie
- Cambio de refacciones
    - Banda
    - Rodillo
    - Cabezal
    - Sensor
- IP
- Zona de Operación
- Operador
- Ubicación
- Comentarios

Permite incorporar la cantidad de registros necesarios en diversas bases de datos, y adjuntar un archivo de series autorizadas, mediante el cual el sistema coteja las series capturadas con las registradas por el coordinador en el documento fuente. Al concluir, se facilita la firma del documento por ambas partes: el responsable de Dataware Soluciones y el responsable del cliente en cuestión. Se registran el asunto del informe, el tipo de llamada, el número de ticket, el nombre del cliente, su dirección de correo electrónico y su número de teléfono celular.

Esta actividad genera y adjunta al correo electrónico dos archivos: un informe en PDF y otro en formato Excel.

**El archivo fuente o de series autorizadas para Bocar debe incluir en formato CSV las siguientes columnas sin encabezados:**

<!-- | Número | Modelo | Serie | Cabezal | Sensor | Rodillo | Banda | IP | Estación | Operador | Ubicación | Fecha Inicio | Fecha Final | Observaciones |
|--------|--------|-------|---------|--------|---------|-------|----|----------|----------|-----------|--------------|-------------|---------------|
|  |  |  |  |  |  |  |  |  |  |  |  |  |  | -->

<!-- Aqui hay un [**ejemplo**](/assets/Excel/bocar_qro_series.csv) de como debe ser el **archivo fuente para Bocar**. -->

Dicho archivo se **descarga** al pulsar el botón de color azul que está sobre el botón **"Agregar nueva base de datos"** o con el signo **"+"**
Una vez descargado el archivo, si se actualiza se **puede enviar a coordinación** al pulsar de nuevo el mismo botón y eligiendo la opción de **"Enviar Series"**

---
<!-- ## Mercado Libre

En la Actividad de **Mercado Libre** se capturan datos como: 

- Modelo
- Numero de Serie
- Cambio de refacciones
    - Banda
    - Rodillo
    - Cabezal
    - Sensor
- Pulgadas o Firmware
- Comentarios

Permite ingresar la cantidad necesaria de registros en varias bases de datos, y adjuntar un archivo de series autorizadas. Este archivo permite al sistema comparar las series capturadas con las registradas por el coordinador en el documento fuente. Una vez finalizada la tarea, se facilita la firma del documento por ambas partes: el responsable de Dataware Soluciones y el responsable del cliente en turno. Se registran el asunto del informe, el tipo de llamada, el número de ticket, el nombre del cliente, su dirección de correo electrónico y su número de teléfono celular.

Como resultado, esta actividad genera y adjunta al correo electrónico dos archivos: un informe en PDF y otro en formato Excel.

**El archivo fuente o de series autorizadas para Mercado Libre debe contener en formato CSV las siguientes cuatro columnas sin encabezados:**

| Serie | Fecha Vigencia Inicial | Fecha Vigencia Final | Zona de Operación |
|----- |------|---------|----------|
|  |  |  |  |

Aqui hay un [**ejemplo**](/assets/Excel/MeLi_Qro_Series.csv) de como debe ser el **archivo fuente para Mercado Libre**.

*La actividad relacionada con **Firmware** sigue el mismo procedimiento, simplemente reemplaza el valor de las pulgadas con el de Firmware.*

--- -->

## Reportes de Servicio

En la Actividad de **Reportes de Servicio** se capturan datos como:

- Número de Serie
- Nombre del Cliente
- Responsable del Cliente
- Teléfono
- Correo electrónico
- Dirección
- Modelo
- Asunto del reporte
- Comentarios respecto al reporte o problema
- Resolución del reporte o problema

Esta actividad opera exclusivamente con un archivo de registros denominado **Datos_RS**, en el cual el usuario puede crear tantos registros como desee. Los números de serie de estos registros se muestran en un Spinner que, al seleccionar uno, completa automáticamente los demás campos con la información correspondiente.

**No se necesita un archivo de series autorizadas para esta actividad, y produce un informe por dispositivo o número de serie.**

---
## Reportes
Aqui hay ejemplos de como son los reportes para cada actividad.

- [**Reporte PDF Otros Cientes**](/assets/PDF/Reporte_ST_Dataware_Qro.pdf)
- [**Reporte PDF Bocar**](/assets/PDF/Reporte_ST_Bocar_Qro.pdf)
- [**Reporte Excel Bocar**](/assets/Excel/Bocar_Qro_Excel.xls)
<!-- - [**Reporte PDF Mercado Libre**](/assets/PDF/Reporte_ST_MeLi_Qro.pdf)
- [**Reporte Excel Mercado Libre**](/assets/Excel/MeLi_Qro_Excel.xls) -->
- [**Reporte de Servicio**](/assets/PDF/Reporte_Servicio_Dataware.pdf)


---
## Créditos

<center>

![](/assets/images/logo_sit_512.png) 
[![](/assets/images/ECMFooterCut.png)](https://github.com/EsCumDW)

</center>



---
## Soporte

 Si tienes dudas o necesitas una aclaración manda email a [e.cuadra@dataware.com.mx](https://google.com). 



