<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>


## Análisis estático de código fuente – Sonarqube y  Sonar-Scanner
El análisis estático de software es un tipo de análisis que se realiza sin ejecutar el programa (el análisis realizado sobre los programas en ejecución se conoce como análisis dinámico de software). El análisis se realiza en el código fuente y en otros casos se realiza en el código objeto.

Para mis desarrollos utilizo un analizador estático de código para ir viendo buenas prácticas, encontrar si existen vulnerabilidades comunes de desarrollo de varios lenguajes.

El analizador que utulizo se llama Sonarqube (software libre) y tiene soporte para 27 lenguajes entre ellos (Java, PHP, JavaScript, etc.).

Les quiero mostrar como tener instalado Sonarqube y luego como hacer el escaneo de un código fuente para que vean como se hace.

Obs:

Asumo que se tiene instalado Docker.

Entramos a la terminal y tecleamos lo siguiente:
    docker pull sonarqube

Crear contenedor:(ver los puertos 9095 y 9092 no este ocupado)
    docker run -d --name sonarqube -p 9095:9000 -p 9092:9092 sonarqube

Entrar al navegador y teclear en la barra de direcciones:

http://localhost:9095
Credenciales por defecto:
User: admin
Pass: admin
Cambiamos el password a 123456

Crear archivo sonar-project.properties

Para escanear un código fuente es necesario tener una imagen de sonar-scanner:
    docker pull newtmitch/sonar-scanner

Corremos:
Linux/MacOS
    docker run -ti -v /pwd:/usr/src --link sonarqube newtmitch/sonar-scanner

Microsoft Windows 10
    docker run -ti -v C:\Users\joseg\repositoriosGit\api-paraguayos:/usr/src --link sonarqube newtmitch/sonar-scanner
