Framework de Automatización de Pruebas Web con Selenium y TestNG
1. Descripción del Proyecto
Este repositorio contiene un framework de automatización de pruebas funcionales diseñado para validar la aplicación web DemoBlaze (https://www.demoblaze.com/). El proyecto está construido sobre una arquitectura robusta y escalable utilizando el patrón de diseño Page Object Model (POM) para garantizar la mantenibilidad y reutilización del código.

El objetivo principal de este framework es automatizar los flujos críticos de la aplicación, incluyendo el registro de usuarios, inicio de sesión y el proceso de compra de extremo a extremo, asegurando la calidad y estabilidad del software.

2. Características Principales
Patrón de Diseño Page Object Model (POM): Separa la lógica de las pruebas de la definición de los elementos de la UI, haciendo el código más limpio y fácil de mantener.

Selenium WebDriver: Utilizado como la librería principal para la interacción y control del navegador web.

TestNG Framework: Empleado para la estructuración de las pruebas, ejecución, aserciones y gestión del ciclo de vida de las mismas (@Test, @BeforeMethod, etc.).

Gestión con Maven: Todas las dependencias y el ciclo de vida del proyecto son gestionados a través de Maven, facilitando la configuración del entorno.

Reportes Avanzados: Integración con dos de las herramientas de reportería más potentes:

Allure Framework: Para generar reportes interactivos, detallados y visualmente atractivos.

ExtentReports: Para crear informes en formato HTML con dashboards y análisis de la ejecución de las pruebas.

3. Prerrequisitos
Para poder clonar y ejecutar este proyecto en un entorno local, necesitarás tener instalado lo siguiente:

Java JDK 21 o superior.

Apache Maven 3.6 o superior.

Un navegador web compatible, como Google Chrome.

Allure Commandline (para generar los reportes de Allure). Puedes instalarlo siguiendo las instrucciones oficiales.

4. Instalación y Configuración
Sigue estos pasos para configurar el proyecto en tu máquina local:

Clonar el Repositorio:

git clone https://github.com/marlonfelipe/demoblazeautomation
cd [nombre-del-directorio]

Instalar Dependencias: Maven se encargará de descargar todas las librerías necesarias definidas en el pom.xml.

mvn clean install

5. Ejecución de las Pruebas
Puedes ejecutar la suite completa de pruebas utilizando el siguiente comando de Maven desde la raíz del proyecto.

mvn test

TestNG ejecutará todas las clases de prueba configuradas. Los resultados de la ejecución se generarán en el directorio target.

6. Visualización de Reportes
Una vez finalizada la ejecución de las pruebas, puedes generar y visualizar los reportes.

6.1. Reporte de Allure
Generar el Reporte: Después de ejecutar mvn test, los resultados de Allure se guardarán en la carpeta target/allure-results. Para visualizar el reporte web, ejecuta:

allure serve target/allure-results

Este comando abrirá automáticamente un reporte interactivo en tu navegador.

6.2. Reporte de ExtentReports
El reporte de ExtentReports se generará como un archivo HTML. La configuración para la ruta de salida deberá ser añadida en una clase de utilidad, pero típicamente se guarda en un directorio como target/reports/ExtentReport.html.

7. Estructura del Proyecto
El proyecto sigue una estructura estándar de Maven y POM para una clara separación de responsabilidades:

src/main/java: Contiene las clases del Page Object Model (pages) y cualquier otra clase de utilidad (utils). Este es el núcleo del framework.

src/test/java: Contiene las clases de prueba (tests) que utilizan los Page Objects para ejecutar los flujos y realizar las aserciones. También incluye la clase BaseTest para la configuración común.

pom.xml: Archivo de configuración de Maven que gestiona todas las dependencias, plugins y el ciclo de vida del build.
