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

php artisan make:controller UsersController  para crear un controlador 

--> blade -- template system / template engiene

controller --> flujo de datos, interaccion
model --> logica, regla de validacion 
view --> capa de representacion 
creamos la tabla post
php artisan make:migration create_posts_table --create=posts 

https://www.easylaravelbook.com/blog/creating-a-hasmany-relation-in-laravel-5/

cuando se crea un nuevo proyecto hay un problema en las migraciones

y esque falta agregar una sentencia en el archivo appServiceProvider.php

use Illuminate\Support\Facades\Schema;

public function boot()
    {
        //
        Schema::defaultStringLength(150);
    }

//-----------------------------------
ahora creamos el modelo de Post 
php artisan make:model Post

//-------------------
libreria para ver registros y crear nuevos desde consola
php artisan tinker

$user= App\User::find(1)

$post 0 new App\Post;

$post->title="laravel 2019"
$post->body="este es el cuerpo del post";
$post->user_id = $user_id
Spost->save()

$user->posts
$post = App\Post::find(1)

/******************************************
si vamos a utilizar tablas que ya estan creadas y no vamos a migrar entonces debemos crear el modelo
php artisan make:model Comment

<!--	@foreach($media as $media)
								<li>{{$user->name}}
								<div class="well">
									@foreach($media->posts as $post)
										<strong>{{$post->title}}</strong>
									@endforeach
								</div>
								<div class="alert alert-info">
									@foreach($media->comments as $comment)
										<strong>{{$comment->body}}</strong>
									@endforeach
								</div>
								
								</li>
							@endforeach-->

{{$users->title_app}}