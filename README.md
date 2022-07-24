## docker-laravel
## Usage
1. create and start containers
    ```
    $ docker-compose up -d
    ```
2. composer install
    ```
    $ docker exec -it slim bash
    $ composer install
    ```
3. start local development server  
    ```
    $ php -S 0.0.0.0:80 -t public
    ```

## Features
### xdebug setting for VSCode
1. install [PHP Debug](https://marketplace.visualstudio.com/items?itemName=xdebug.php-debug)
2. setting `.vscode/launch.json`

    /.vscode/launch.json
    ```
    {
        "version": "0.2.0",
        "configurations": [
            {
                "name": "Listen for Xdebug",
                "type": "php",
                "request": "launch",
                "port": 9003,
                "pathMappings": {
                    "/var/www/html/": "${workspaceRoot}/src/public/"
                }
            },
        ]
    }
    ```
Referens  
launch.json attribute  
https://code.visualstudio.com/docs/editor/debugging#_launchjson-attributes  
about pathMappings  
https://marketplace.visualstudio.com/items?itemName=xdebug.php-debug  

/php.ini  
https://xdebug.org/docs/all_settings
#### Usage
1. Ctrl+Shift+D
2. ▶︎(RUN) 「Listen for Xdebug」 selection
3. Set a breakpoint on any line
4. F5 or ▶︎ click to debag start
