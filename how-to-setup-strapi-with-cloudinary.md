# How to Setup Strapi with Cloudinary

```
yarn add strapi-provider-upload-cloudinary graphql
touch config/plugins.js
```

```js
// ./config/plugins.js
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

```
# .env
CLOUDINARY_NAME = cloudinary-name
CLOUDINARY_KEY = cloudinary-key
CLOUDINARY_SECRET = cloudinary-secret
```
