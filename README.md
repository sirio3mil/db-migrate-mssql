# db-migrate-mssql
Updated mssql driver for db-migrate

## Installation

```
npm install db-migrate-mssql
```

## Configuration

Example database.json file

```
{
  "defaultEnv": "local",
  "local": {
    "driver": "mssql",
    "user": {"ENV": "DATABASE_USER"},
    "password": {"ENV": "DATABASE_PASSWORD"},
    "host": {"ENV": "DATABASE_HOST"},
    "database": {"ENV": "DATABASE_NAME"}
  }
}
```

## Troubleshooting

In case of `Error got unwanted exception: Failed to connect to host:1433 - self signed certificate` set `trustServerCertificate` option to true

```
{
  "defaultEnv": "local",
  "local": {
    "driver": "mssql",
    "user": {"ENV": "DATABASE_USER"},
    "password": {"ENV": "DATABASE_PASSWORD"},
    "host": {"ENV": "DATABASE_HOST"},
    "database": {"ENV": "DATABASE_NAME"},
    "options": {
      "trustServerCertificate": true
    }
  }
}
```
