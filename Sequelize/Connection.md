```js
const Sequelize = require('sequelize');
const MessageModel = require('./message');
const UserModel = require('./users');

const config = {
  host: 'localhost',
  dialect: 'postgres',
  logging: false
};

const sequelize = new Sequelize('db-name', 'username', 'password', config);

const db = {};

db.sequelize = sequelize;
db.Message = MessageModel(sequelize, Sequelize.DataTypes);
db.User = UserModel(sequelize, Sequelize.DataTypes);

// associations
db.Message.associate(db);
db.User.associate(db);

module.exports = db;
```
