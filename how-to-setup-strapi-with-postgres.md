# How to Setup Strapi with Postgres

Make sure postgres is configured and running and create a new database:

```
createdb backend
```

Then run the strapi generator:

```
yarn create strapi-app backend
```

Select postgres as your database and enter your credentials.

Once the generator runs, `cd` into the directory and run `yarn develop`.
