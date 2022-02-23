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

### Self signed certificate

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

### Missing migrations folder

`Error got unwanted exception: ENOENT: no such file or directory, scandir '/migrations'`

Migrations folder is not created by default, you need to do it manually

### Incorrect syntax near 'GO'

In case of `sql-file` output do not use `GO` as query ending, use `;` instead

### Freezing

If migrations execution freeze try to avoid doing it inside transaction with `--non-transactional` option
