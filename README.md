# Docker - Laravel skeleton

![Banner](./banner.svg)

Easily create a new Dockerize laravel application by download a fresh Laravel installation from the [official GitHub repository](https://github.com/laravel/laravel) and run a few statements to initialize Docker and set-up the application.

## How to use

1. Copy every commands here below
2. Open a DOS Prompt Session
3. Press <kbd>CTRL</kbd>+<kbd>C</kbd> to run them

```bash
mkdir c:\projects\laravel_app
cd c:\projects\laravel_app
git clone https://github.com/cavo789/docker_laravel .
curl -LJO https://github.com/laravel/laravel/archive/v8.5.9.zip
powershell -command "Expand-Archive laravel-8.5.9.zip -DestinationPath . -Force"
del v8.5.9.zip

copy .env.example .env

# mkdir .docker
# copy .\.docker\Dockerfile .docker\Dockerfile
# copy .\.docker\vhost.conf .docker\vhost.conf
copy .\.docker\docker-compose.yml .\docker-compose.yml

docker-compose up -d

docker-compose exec app composer install
docker-compose exec app php artisan key:generate

"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" http://127.0.0.1:8080
```
