# DRIS V4.0.2 - SAP V1.0.0 (Dataware Report Integrated System)

<center>

![](/assets/images/DatawareOKnegro.png)

</center>

<center>

[![Dataware](https://img.shields.io/badge/-Dataware-yellow)](https://www.dataware.com.mx/)
[![ST](https://img.shields.io/badge/-Soporte%20T%C3%A9cnico-darkred)](https://www.dataware.com.mx/soporte-tecnico)
[![Android app](https://img.shields.io/badge/Android-App-blue)](https://developer.android.com/?hl=es-419)
[![SIT](https://img.shields.io/badge/SIT-Dev-lightblue?style=plastic\&logo=SIT\&logoColor=blue)](https://www.dataware.com.mx/servicios-profesionales)
[![SAP](https://img.shields.io/badge/SAPB1-ServiceLayer-orange?style=plastic\&logo=SIT\&logoColor=blue)](https://www.dataware.com.mx/servicios-profesionales)

</center>

---



## Introducción

El departamento de **Servicios de Integración Tecnológica (SIT)** y el equipo de **Soporte Técnico** rediseñaron la aplicación de **captura de reportes** utilizando **Android Studio**, reemplazando la versión anterior desarrollada en Kalipso. Este rediseño tiene como objetivo mejorar la robustez del sistema, ofrecer una experiencia de usuario más fluida y alinearse con la plataforma **SIID**.

La aplicación **DRIS** está diseñada para facilitar la generación de reportes por parte del personal técnico y de servicios, permitiendo documentar mantenimientos y servicios conforme al cliente atendido y al rol del usuario.

### Funcionalidades principales

* Creación de tickets de mantenimiento y servicio en SAP
* Conteo de registros
* Vista previa de registros, tickets pendientes y tickets globales
* Mayor espacio en comentarios
* Reportes específicos por cliente:
  * Reporte Excel de Mantenimiento (solo para Bocar)
  * Reporte PDF de Mantenimiento por Ticket Global
  * Reporte PDF de Servicio por ticket
* Envío de reportes por correo electrónico
* Edición de firmas antes de generar PDF
* Cambio de cliente
* Creación de archivos de registros
* Borrado de archivos de registros
* Borrado de registros, tickets y globales

---

## Restricciones y condiciones de uso

Para garantizar un funcionamiento correcto y una adecuada gestión de información, se definen las siguientes condiciones y restricciones según el **rol del usuario**:

### Creación de Tickets

| Actividad                      | Rol Técnico                                  | Rol SIT                                                                         |
| ------------------------------ | -------------------------------------------- | ------------------------------------------------------------------------------- |
| Tickets de Mantenimiento       | ✔ Puede crear tickets cerrados por impresora | ✔ Puede crear tickets cerrados por impresora                                    |
| Tickets de Mantenimiento Bocar | ✔ Puede crear tickets cerrados por impresora | ✔ Puede crear tickets cerrados por impresora                                    |
| Tickets de Servicio            | ❌ No disponible                              | ✔ Puede generar un ticket abierto por servicio y cerrarlo al generar el reporte |

⚠️ **Importante:** *Para garantizar el correcto funcionamiento de la aplicación y su integración con **SAP**, asegúrate de tener activa la conexión **VPN**. Consulta el manual de configuración [**Forti Client VPN** ](assets/images/Manual%20FortiVPN%20DRIS.png)si tienes dudas respecto a como configurar tu VPN.*

### Creación de Reportes

Ambos roles pueden generar reportes finales de mantenimiento o servicio. Estos reportes pueden ser:
* Compartidos con el cliente por correo electrónico
* Adjuntados automáticamente en **SAP**
  * En el **ticket global** (para mantenimientos)
  * En el **ticket en curso** (para servicios)

---

<!-- ## Niveles de acceso por rol

| Rol     | Tickets Mantenimiento | Tickets Mantenimiento Bocar | Tickets Servicio | Creación de Reportes |
| ------- | --------------------- | --------------------------- | ---------------- | -------------------- |
| Técnico | ✔                     | ✔                           | ❌                | ✔                    |
| SIT     | ✔                     | ✔                           | ✔                | ✔                    |

--- -->

## Funciones y responsabilidades por rol

Aunque existen dos roles diferenciados (Técnico y SIT), ambos pueden acceder a todas las funciones generales de la aplicación. La única restricción significativa es la **creación de tickets**:

* **Técnico**: puede crear tickets **solo en actividades de mantenimiento**.
* **SIT**: puede crear tickets **en todas las actividades**.

---

## Reportes de Mantenimiento

En la Actividad de **Reportes de Mantenimiento** se capturan datos como:

* Modelo
* Número de Serie
* Cambio de refacciones:
  * Banda
  * Rodillo
  * Cabezal
  * Sensor
* Pulgadas del encoder
* Comentarios

Esta sección permite la inclusión de múltiples registros en diversas bases de datos según sea necesario. Cada registro, si la serie existe en SAP, es un ticket. El documento generado es firmado por ambas partes: el responsable de Dataware Soluciones y el responsable del cliente actual. Además, se registran el asunto del reporte, el tipo de llamada y el número de ticket Global.

Como resultado de esta actividad, se genera y adjunta al ticket Global en SAP un **reporte en formato PDF**  y se manda por correo al cliente y a la coordinación pertinente.

---

## Reportes de Mantenimiento Bocar

En la Actividad de **Reportes de Mantenimiento Bocar** se capturan datos como:

* Modelo
* Número de Serie
* Cambio de refacciones:
  * Banda
  * Rodillo
  * Cabezal
  * Sensor
* IP
* Zona de Operación
* Operador
* Ubicación
* Comentarios

Permite incorporar múltiples registros en diversas bases de datos y validar las series autorizadas contra un archivo fuente provisto por coordinación. Al finalizar, el reporte es firmado por ambas partes, se registran los datos de contacto del cliente y se adjuntan al correo electrónico. Además, se registran el asunto del reporte, el tipo de llamada y el número de ticket Global.
Como resultado de esta actividad, **se generan y adjuntan al ticket Global en SAP un reporte en formato PDF y un reporte en formato Excel**, los cuales se envían por correo tanto al cliente como a la coordinación pertinente.

---

## Reportes de Servicio

En la Actividad de **Reportes de Servicio** se capturan datos como:

* Número de Serie
* Nombre del Cliente
* Responsable del Cliente
* Teléfono
* Correo electrónico
* Dirección
* Modelo
* Asunto del reporte
* Comentarios
* Resolución del reporte o problema

Esta actividad opera **por ticket:** cada registro genera un **reporte individual** y se crea un **ticket de servicio único** que se **cierra automáticamente** al generar el reporte.
Al momento de armar el reporte, se solicita al usuario que ingrese su **nombre**, el **asunto del servicio** y un número de **ticket Global provisional.**
El reporte generado se **adjunta automáticamente al ticket en SAP.**

---

## Reportes

Aquí hay ejemplos de reportes generados por la aplicación:

* [**Reporte Mantenimiento**](/assets/PDF/Reporte_ST_Dataware_Qro.pdf)
* [**Reporte Mantenimiento Bocar**](/assets/PDF/Reporte_ST_Bocar_Qro.pdf)
* [**Reporte Mantenimiento Excel Bocar**](/assets/Excel/Bocar_Qro_Excel.xls)
* [**Reporte de Servicio**](/assets/PDF/Reporte_Servicio_Dataware.pdf)

---

## Tecnologías

![java](https://img.shields.io/badge/Java-yellow?style=for-the-badge\&logo=Android%20Studio\&logoColor=white\&labelColor=black)
![Gradle](https://img.shields.io/badge/Gradle-purple?style=for-the-badge\&logo=Gradle\&logoColor=white\&labelColor=black)
![Zebra](https://img.shields.io/badge/Zebra-grey?style=for-the-badge\&logo=zebratechnologies\&logoColor=white\&labelColor=black)
![SAPB1](https://img.shields.io/badge/SAPB1-orange?style=for-the-badge\&logo=SAP\&logoColor=white\&labelColor=black)

---

## Créditos

<center>

![](/assets/images/logo_sit_512.png)
<!-- [![](/assets/images/ECMFooterCut.png)](https://github.com/EsCumDW) -->

</center>

---

## Soporte

Si tienes dudas revisa el [Manual de Usuario DRIS](assets/PDF/Manual%20de%20Usuario%20DRIS.pdf) o si necesitas soporte, manda un email a [e.cuadra@dataware.com.mx](mailto:e.cuadra@dataware.com.mx).
