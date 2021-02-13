# Docker - Laravel skeleton

![Banner](./banner.svg)

Easily create a new Dockerize laravel application by download a fresh Laravel installation from the [official GitHub repository](https://github.com/laravel/laravel) and run a few statements to initialize Docker and set-up the application.

## How to use

1. Create a new, empty, folder on your disk (let's say `c:\projects\laravel_app`),
2. Open a DOS Prompt Session and go inside that folder (`cd c:\projects\laravel_app`),
3. Copy every commands here below
4. Press <kbd>CTRL</kbd>+<kbd>C</kbd> to run them

```bash
git clone https://github.com/cavo789/docker_laravel .
curl -o laravel.zip -LJO https://github.com/laravel/laravel/archive/v8.5.9.zip
powershell -command "Expand-Archive laravel.zip -DestinationPath . -Force"
del laravel.zip
cd laravel-8.5.9
copy .env.example .env
mkdir .docker
copy .\..\.docker\Dockerfile .docker\Dockerfile
copy .\..\.docker\vhost.conf .docker\vhost.conf
copy .\..\.docker\docker-compose.yml .\docker-compose.yml
docker-compose up -d
docker-compose exec app composer install && php artisan key:generate
```

When finished, start a new browser and open `http://127.0.0.1:8080`, your Laravel site will be up and running.

## Notes

- The instructions below use the latest known version of Laravel at the time of writing this documentation. Go to [https://github.com/laravel/laravel/tags](https://github.com/laravel/laravel/tags) to see the latest version at the time you read this document. So, change the `8.5.9` version number in the instructions here above with the desired laravel version.
- The Laravel database will be stored in a volume; not on disk. The volume is called `mydata` and will remains available until you run a `docker-compose stop` command (still remains with a `docker-compose down`).
