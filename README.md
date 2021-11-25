# Strapi—Boilerplate 

1. I simply run the command `npx create-strapi-app my-project --quickstart`.
2. I create a `/.env`  file for the AWS credentials.
```
AWS_ACCESS_KEY_ID=XXX
AWS_ACCESS_SECRET=XXX
AWS_REGION=XXX
AWS_BUCKET_NAME=XXX
```
3. I create a `config/plugins.js` to upload to AWS-S3.
```javascript
module.exports = ({ env }) => ({
  upload: {
    provider: "aws-s3",
    providerOptions: {
      accessKeyId: env("AWS_ACCESS_KEY_ID"),
      secretAccessKey: env("AWS_ACCESS_SECRET"),
      region: env("AWS_REGION"),
      params: {
        Bucket: env("AWS_BUCKET_NAME"),
      },
    },
  },
});
```
4. To publish the application on Heroku, I just follow the [Strapi Documentation](https://strapi.io/documentation/developer-docs/latest/setup-deployment-guides/deployment/hosting-guides/heroku.html).

---

[@benitodotcool](https://www.instagram.com/benitodotcool/) | [benito.cool](https://benito.cool/)