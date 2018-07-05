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
/*************************************************/
<!doctype html>
<html lang="{{ app()->getLocale() }}">
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1">

        <title>Conexion Grafica</title>

        <!-- Fonts -->
        <link href="https://fonts.googleapis.com/css?family=Raleway:100,600" rel="stylesheet" type="text/css">

        <!-- Styles -->
        <style>
            html, body {
                background-color: #fff;
                color: #636b6f;
                font-family: 'Raleway', sans-serif;
                font-weight: 100;
                height: 100vh;
                margin: 0;
            }

            .full-height {
                height: 100vh;
            }

            .flex-center {
                align-items: center;
                display: flex;
                justify-content: center;
            }

            .position-ref {
                position: relative;
            }

            .top-right {
                position: absolute;
                right: 10px;
                top: 18px;
            }

            .content {
                text-align: center;
            }

            .title {
                font-size: 84px;
            }

            .links > a {
                color: #636b6f;
                padding: 0 25px;
                font-size: 12px;
                font-weight: 600;
                letter-spacing: .1rem;
                text-decoration: none;
                text-transform: uppercase;
            }

            .m-b-md {
                margin-bottom: 30px;
            }
        </style>
    </head>
    <body>
        <div class="flex-center position-ref full-height">
            @if (Route::has('login'))
                <div class="top-right links">
                    @auth
                        <a href="{{ url('/home') }}">Home</a>
                    @else
                        <a href="{{ route('login') }}">Login</a>
                        <a href="{{ route('register') }}">Register</a>
                    @endauth
                </div>
            @endif

            <div class="content">
                <div class="title m-b-md">
                    Laravel
                </div>

                <div class="links">
                    <a href="https://laravel.com/docs">Documentation</a>
                    <a href="https://laracasts.com">Laracasts</a>
                    <a href="https://laravel-news.com">News</a>
                    <a href="https://forge.laravel.com">Forge</a>
                    <a href="https://github.com/laravel/laravel">GitHub</a>
                </div>
            </div>
        </div>
    </body>
</html>
