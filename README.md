This package wraps the mysql nodejs client package (https://www.npmjs.com/package/mysql) into an async/await library.

## Basic Example

```javascript
const { makeDb } = require('mysql-async-simple');
const mysql = require("mysql");

const connection = mysql.createConnection({
    host: process.env.HOST,
    user: process.env.USER,
    password: process.env.PASSWORD,
    database: process.env.DB
});
const db = makeDb();
await db.connect(connection);

try {
    const users = await db.query(connection, 'SELECT * FROM users');
} catch (e) {
    // handle exception
} finally {
    await db.close(connection);
}
```

For more information visit github
https://github.com/hashgit/mysql-async-simple#readme

