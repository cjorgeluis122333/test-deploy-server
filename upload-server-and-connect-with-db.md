# Koyeb
Here you upload your server sharing your repository
```
https://www.koyeb.com/
```

## Steep 1: Create the service
1. Push in the button Create Service 
2. Select ***Web service***
3. Push in the icon of GitHub


# Configure Buildpack

## Build command:
```shell
composer install --no-dev --optimize-autoloader && php artisan config:cache && php artisan route:cache
```

## Run command
```shell
php artisan migrate --force && php artisan serve --host=0.0.0.0 --port=$PORT
```

# Environment variables and files
NAME                 VALUE    
APP_DEBUG            fasle
APP_ENV              production
APP_KEY              base64:hRPHGdX1I1bvjOVVjSd/ANSZTXq3Im0EX+hdvovNdYk=
APP_URL              https://ugliest-aleece-jorgeluis-d39b7ba0.koyeb.app
DB_CONNECTION        mysql
DB_DATABASE          test
DB_HOST              gateway01.us-east-1.prod.aws.tidbcloud.com
DB_PASSWORD          fDxEvv0ayeZhzKyM
DB_PORT              4000
DB_USERNAME          3nk742z2pwnHJeJ.root
MYSQL_ATTR_SSL_CA    /etc/ssl/certs/ca-certificates.crt
SESSION_DRIVER       cookie



# Instance CPU Eco 
Washington, D.C

# Ports
```
Port   Protocol
8000   HTTP 
Path   /
```
