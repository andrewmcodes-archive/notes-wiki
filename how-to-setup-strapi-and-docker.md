# How to Setup Strapi and Docker

## Install Docker

```
brew install --cask docker
```

>[jesseduffield/lazydocker](https://github.com/jesseduffield/lazydocker) is a docker tool I cannot live without.

## Setup

```
mkdir strapi
cd strapi
touch docker-compose.yml
```

```yml
# docker-compose.yml

version: '3'

services:
  strapi:
    container_name: strapi
    image: strapi/strapi
    environment:
      - DATABASE_CLIENT=postgres
      - DATABASE_HOST=db
      - DATABASE_PORT=5432
      - DATABASE_NAME=strapi
      - DATABASE_USERNAME=strapi
      - DATABASE_PASSWORD=strapi
    ports:
      - 1337:1337
    volumes:
      - ./app:/srv/app
    depends_on:
      - db

  db:
    container_name: postgres
    image: postgres
    restart: always
    volumes:
      - ./db:/var/lib/postgresql/data
    environment:
      POSTGRES_USER: strapi
      POSTGRES_PASSWORD: strapi
      POSTGRES_DB: strapi
```

## Setup Strapi

```
docker-compose up -D
```

This will take a good minute - watch the logs to know when it's ready. This will auto create a strapi app for us since one does not already exist. When the site is ready, you will see a notice in the logs that it is available at `http://localhost:1337/admin/`. Go to that URL and you will be prompted to create a new account. After you do that you will be in your new strapi cms.

![image](https://github.com/andrewmcodes/notes-wiki/raw/master/images/Wed_Mar_10_2021_1615356497181.png)

## Install Plugins

Go to the marketplace tab and install the GraphQL and Documentation plugins.

![image](https://github.com/andrewmcodes/notes-wiki/raw/master/images/Wed_Mar_10_2021_1615356565638.png)

Strapi will restart but this doesn't always work so you may need to restart the container. You can tell by watching the logs and checking for errors or determining if it has stalled somewhere. Just restart the container.

### Cloudinary


```bash
yarn add strapi-provider-upload-cloudinary graphql
touch app/config/plugins.js
touch .env
```

```conf
# .env
CLOUDINARY_NAME = cloudinary-name
CLOUDINARY_KEY = cloudinary-key
CLOUDINARY_SECRET = cloudinary-secret
```

```js
// app/config/plugins.js
module.exports = ({ env }) => ({
  upload: {
    provider: "cloudinary",
    providerOptions: {
      cloud_name: env("CLOUDINARY_NAME"),
      api_key: env("CLOUDINARY_KEY"),
      api_secret: env("CLOUDINARY_SECRET"),
    },
  }
});
```
