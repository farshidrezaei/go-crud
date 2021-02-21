# Go-Crud

Simple Crud With golang and mysql

## Usage

### Step 1:

Prepare and Import MySQL driver into your project Using Terminal first install driver for Go's MySQL database package.
Run below command and install MySQL driver's

```shell
go get -u github.com/go-sql-driver/mysql
```

Now create go_crud Database

1. Open PHPMyAdmin/SQLyog or what ever MySQL database management tool that you are using.
2. Create a new database "go_crud"

### Step 2:

Creating the Users Table Execute the following SQL query to create a table named users inside your MySQL database.
We will use this table for all of our future operations.

```mysql
DROP TABLE IF EXISTS users;
CREATE TABLE users
(
    id   int(6) unsigned NOT NULL AUTO_INCREMENT,
    name varchar(30)     NOT NULL,
    age varchar(30)     NOT NULL,
    PRIMARY KEY (id)
) ENGINE = InnoDB
  AUTO_INCREMENT = 1
  DEFAULT CHARSET = utf8;
```

* You can use your own db driver and configure. just open `main.go` and edit `dbConn()` function:
```go
func dbConn() (db *sql.DB) {
	dbDriver := "mysql"
	dbUser := "root"
	dbPass := ""
	dbName := "go_crud"
	db, err := sql.Open(dbDriver, dbUser+":"+dbPass+"@/"+dbName)
	if err != nil {
		panic(err.Error())
	}
    return db
}
 ```

### Step 3:

Run the following command in terminal
```shell
go run main.go
```
