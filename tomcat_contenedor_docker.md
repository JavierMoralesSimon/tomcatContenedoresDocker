# Tomcat en contenedor Docker

## Descarga de una imagen oficial de Tomcat
Realizamos dicha acción mediante el comando `docker pull tomcat:latest`.
![](https://github.com/JavierMoralesSimon/tomcatContenedoresDocker/blob/main/Capturas/1.png)

## Montado de una aplicación
Mediante el uso de un Dockerfile, realizaremos dicha acción. Los pasos son:
  1. Crear un directorio de trabajo mediante el comando `mkdir -p ~/tomcat-docker/webapps` y colocarnos en la carpeta "tomcat-docker" con `cd ~/tomcat-docker`.
    ![](https://github.com/JavierMoralesSimon/tomcatContenedoresDocker/blob/main/Capturas/2.1.png)
  2. Copiar nuestro archivo .war ahí.
    ![](https://github.com/JavierMoralesSimon/tomcatContenedoresDocker/blob/main/Capturas/2.2.png)
  3. Crear un archivo Dockerfile y darle contenido.
    ![](https://github.com/JavierMoralesSimon/tomcatContenedoresDocker/blob/main/Capturas/2.3.png)
    ![](https://github.com/JavierMoralesSimon/tomcatContenedoresDocker/blob/main/Capturas/2.4.png)
  5. Construir la imagen.
    ![](https://github.com/JavierMoralesSimon/tomcatContenedoresDocker/blob/main/Capturas/2.5.png)
  6. Ejecutar el contenedor.
    ![](https://github.com/JavierMoralesSimon/tomcatContenedoresDocker/blob/main/Capturas/2.6.png)
  7. Abrir la página en el navegador y confirmar que funciona.
    ![](https://github.com/JavierMoralesSimon/tomcatContenedoresDocker/blob/main/Capturas/2.7.png)

## Diferencias entre el Tomcat nativo y el Tomcat en contenedor
| Concepto                | Tomcat Nativo                                   | Tomcat en Contenedor                        |
| ------------------------| ----------------------------------------------- | ------------------------------------------- |
| Instalación             | Se instala directamente en el sistema operativo | Se ejecuta dentro de un contenedor Docker   |
| Aislamiento             | Comparte recursos del host                      | Aislado, con recursos encapsulados          |
| Portabilidad            | Depende del OS y configuración local            | Igual en cualquier máquina con Docker       |
| Escalabilidad           | Manual, más difícil de replicar                 | Fácil de escalar con orquestadores (K8s)    |
| Gestión de dependencias | Depende de Java y paquetes del host             | Incluye dependencias en la imagen           |
| Actualizaciones         | Manual y propenso a inconsistencias             | Se actualiza regenerando la imagen          |
| Reproducibilidad        | Puede variar entre entornos                     | Identica en dev, test y producción          |
| Tiempo de arranque      | Rápido (si está bien configurado)               | Igual o más rápido dependiendo de la imagen |
