# Mfund Backend

## Clone Repositories <a id="clone-repositories"></a>

Mfund Flutter app is a mono repo git project. We need to clone four repositories for flutter app.‌

* mfund-app
* mfund-api-service
* mfund-framework
* mfund-common-modules

```text
mkdir mfund-backend
cd mfund-server-app
git clone <URL for mfund-server-app>
yarn install // You can use `npm install`
```

* Configure Database in `config/db-psql.js` file.
* Get the Firebase admin key.json and add it in root directory.
* Configure Firebase in `config/db-firebase.js` file

### **Online PostgreSQL Databases**

* [ElephantSQL](https://www.elephantsql.com/)
* \*\*\*\*[Heroku](https://www.heroku.com/postgres)
* [AWS RDS](https://aws.amazon.com/rds/postgresql/)

## **Configuration**

```text
// config.env
NODE_ENV=development
PORT=5000
JWT_ISSUER=geekyants
JWT_AUDIENCE=market-mfund-users
JWT_ACCESS_TOKEN_EXPIRES=1d
JWT_REFRESH_TOKEN_EXPIRES=10d
```

* JWT token header can be configured from `config/config.env`.

