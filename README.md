# conexiongrafica
Página web  de la empresa Conexión Gráfica  de la señorita Camila Apraez
version 1.0 San juan de Pasto 19'16'2018

herramientas:

xampp
7.1.4  php 7.1.4  7.2.2
instalacion
configuracion 
arquitectura
-- request lifecycle
--MVC

frontend

ORM object relational mapping

https://www.youtube.com/watch?v=HX4WCUD8jtE

https://getcomposer.org/download/ 


ejecutamos conEmu que es un bash, nos ubicamos en la carpeta de httdocs de xamp

y ejecutamos este comando 

composer  create-project --prefer-dist laravel/laravel appConexion

opcional : laravel/installer laravel new blog 

para correr el servidor nos ubicamos en la carpeta de la app, y ejecutamos 

php artisan serve 

localhost/phpmyadmin


creamos la db


conexion_db
db: conexion_db
user: conexion_db_user
password db proinsalud-pc : qmmFzzcMJIAm32K9

check --- grant all privilegies .... 

en app/kernel se crean los midleware que atrapamos el request y si estalogueado lo redirigimos hacia alguna parte y sino a otra.
tambien para permisos y cosas etc


--- en la consola
php artisan make:auth

php artisan migrate //para migrar a la bd
php artisan migrate:rollback //devolver una migracion
