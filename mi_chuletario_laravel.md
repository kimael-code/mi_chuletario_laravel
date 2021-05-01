# Mi Chuletario Laravel

## Crear Proyecto con Composer

```bash
composer create-project laravel/laravel mi_proyecto

cd mi_proyecto

php artisan serve
```

## Crear Proyecto con Laravel

```bash
composer global require laravel/installer

laravel new mi_proyecto

cd mi_proyecto

php artisan serve
```

## Crear Proyecto y Repositorio Git con Laravel

*Solamente posible si el paquete `laravel/installer` se instaló como dependencia global de Composer.*

```bash
laravel new mi_proyecto --git

# con GitHub
laravel new mi_proyecto --github
laravel new mi_proyecto --github="--public"
laravel new mi_proyecto --github="--public" --organization="laravel"
```

## Crear Proyecto con Docker (Contenedores)

```bash
curl -s https://laravel.build/mi_proyecto | bash

cd mi_proyecto

./vendor/bin/sail up
```

## Crear Proyecto con Docker (Contenedores) + Servicios

*Los servicios disponibles, al momento de escribir este chuletario, son: `mysql`, `pgsql`, `redis`, `memcached`, `meilisearch`, `selenium`, y `mailhog`.*

```bash
curl -s "https://laravel.build/mi_proyecto?with=pgsql,redis" | bash

cd mi_proyecto

./vendor/bin/sail up
```

## Definir `sail` como Alias (en Linux)

```bash
# en .bash_aliases definir el siguiente alias
alias sail='bash vendor/bin/sail'
```

## Usar `sail`

```bash
# iniciar sail en modo "detached"
sail up -d

# detener sail eliminando volúmenes
sail down --volumes

# ejecutar comandos de PHP
sail php --version

# ejecutar comandos composer
sail composer require laravel/sanctum

# ejecutar comandos artisan
sail artisan queue:work

# ejecutar comandos Node/NPM
sail node --version
sail npm run prod
```

## Publicar Sail

```bash
sail artisan sail:publish
```

## Reconstruir Contenedores Sail

```bash
sail build --no-cache
```
