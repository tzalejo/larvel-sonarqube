<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## Análisis estático de código fuente – Sonarqube y  Sonar-Scanner
Entramos a la terminal y tecleamos lo siguiente:
`docker pull sonarqube`

Crear contenedor:(ver los puertos 9095 y 9092 no este ocupado)
`docker run -d --name sonarqube -p 9095:9000 -p 9092:9092 sonarqube`

Entrar al navegador y teclear en la barra de direcciones:

http://localhost:9095
Credenciales por defecto:
User: admin
Pass: admin
Cambiamos el password a 123456

Crear archivo sonar-project.properties

Para escanear un código fuente es necesario tener una imagen de sonar-scanner:
`docker pull newtmitch/sonar-scanner`
Corremos:
Linux/MacOS
`docker run -ti -v /pwd/proyecto:/usr/src --link sonarqube newtmitch/sonar-scanner` 
ejemplo:
`docker run -ti -v /home/alejandro/Documentos/trabajo/docker-run/backend/tinatombs/server:/usr/src --link sonarqube newtmitch/sonar-scanner`
Microsoft Windows 10
`docker run -ti -v C:\Users\joseg\repositoriosGit\api-paraguayos:/usr/src --link sonarqube newtmitch/sonar-scanner`
