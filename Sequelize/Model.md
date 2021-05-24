## User model

```js
module.exports = (sequelize, DataTypes) => {
  const User = sequelize.define(
    'User',
    {
      username: DataTypes.STRING,
      password: DataTypes.STRING,
      id: {
        type: DataTypes.INTEGER,
        autoIncrement: true,
        primaryKey: true
      }
    },
    { timestamps: false }
  );
  User.associate = (db) => {
    User.hasMany(db.Message),
      {
        foreignKey: 'username'
      };
  };
  return User;
};
```

## Message model

```js
module.exports = (sequelize, DataTypes) => {
  const Message = sequelize.define(
    'Message2',
    {
      UserId: DataTypes.INTEGER,
      content: DataTypes.STRING,
      timestamp: DataTypes.BIGINT,
      id: {
        type: DataTypes.INTEGER,
        autoIncrement: true,
        primaryKey: true
      }
    },
    { timestamps: false }
  );
  Message.associate = (db) => {
    Message.belongsTo(db.User),
      {
        foreignKey: 'author'
      };
  };
  return Message;
};
```

## Queries

```js
const { Message, User } = require('../models/index');

await Message.findAll({ include: [User] });
await User.findAll({ where: { username } });
```
