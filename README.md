# aws-custom-nodejs-oidc-provider-server-on-heroku

**Deploy OIDC Server to Heroku**

1. If git not initialized, init it
    ```sh
    git init
    ```

1. Create a heroku app  
    ```bash
    heroku create --addons securekey,heroku-redis:hobby-dev
    ```
    ![](https://www.evernote.com/l/AAHlRnEvKuhCaIRToznvD5N1UYxRmu9rDC0B/image.png)

1. Enable (experimental) runtime-dyno-metadata
    ```bash
    heroku labs:enable runtime-dyno-metadata
    ```
    ![](https://www.evernote.com/l/AAEe2gZGiLxITLq9aidUWnsiy1S-mXa5Ru0B/image.png)

1. Commit to your local repo  
    ```bash
    git add .
    git commit -a -m 'my initial commit'
    ```

1. Deploy to heroku  
    ```bash
    git push heroku master
    ```

1. Done!  
    ```bash
    heroku open '/.well-known/openid-configuration' # to see your openid-configuration  
    heroku open '/auth?client_id=foo&response_type=code&scope=openid' # to start your first Authentication Request