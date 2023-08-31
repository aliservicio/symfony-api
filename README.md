<img src="https://jorgebenitezlopez.com/github/symfony.jpg">

# Symfony API

Instalación de Symfony y creación de una API

# Requisitos

- Symfony CLI: https://symfony.com/download
- PHP 8.2.3 (cli). Se puede descargar en OSX con: https://formulae.brew.sh/formula/php
- Composer: https://getcomposer.org/download/


# Pasos para la instalación y configuración

- symfony new symfony-api --version=5.4
- cd symfony-api
- symfony composer require api
- composer require --dev symfony/profiler-pack
- (Fíjate que en .env CORS_ALLOW_ORIGIN='^https?://(localhost|127\.0\.0\.1)(:[0-9]+)?$')
- composer require symfony/orm-pack 
- Descomento sqlite y comento postgressql en el .env
- symfony console doctrine:database:create
- symfony console doctrine:schema:create
- Ruta: http://127.0.0.1:8000/api
- composer require symfony/maker-bundle
- composer require form validator twig-bundle security-csrf annotations
- composer require symfony/maker-bundle
- Hacer entidad: php bin/console make:entity. Book y seleccionamos que con API:  Mark this class as an API Platform resource (expose a CRUD API for it)
- Hacer CRUD php bin/console make:crud de Book
- Añadir campos como: Autor, title (Fíjate en el entity. ¿Algo extraño?)
- Poner en el config en api_plaform.ymal: metadata_backward_compatibility_layer: false
- Ruta: http://127.0.0.1:8000/api

# Rutas de la aplicación:

| URL path                    | Description           | 
| :--------------------------:|:---------------------:|
| /api                   |  Api Doc  |
| /book                   |  Listado de libros  |  

# Referencias

- API Platform : https://api-platform.com/docs/distribution/
- Symfony casts about API: https://symfonycasts.com/screencast/api-platform/install?cid=apip
