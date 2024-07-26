# greenlight

Greenlight is a project covered in the book `Let's Go Further`
by Alex Edwards.

I've also made a series of blog posts as I follow along this book, check it out
at [blog.amyndang.me](https://blog.amyndang.me/series/learning%20the%20backend/)

## Setup

### Pre-reqs
Have these programs installed on your machine:
- [migrate cli](https://github.com/golang-migrate/migrate/releases/download/v4.14.1/migrate.linux-amd64.tar.gz)
- [postgresql](https://www.postgresql.org/download/)

### Environment Variables
Create a environment variable with:
```bash
export GREENLIGHT_DB_DSN="postgres://greenlight:password@localhost/greenlight"
```

OR create a `.envrc` file. Use `.envrc_example` as a reference.

## Build & Run
Build API with:
```bash
make db/migrations/new name=db_name
make db/migration/up
make build/api
```

This will create a executable file called `api` in `greenlight/bin/linux_amd64`

Run the executable with:
```bash
make run/api
```

## Deployment
After setting up server, remember to grab IP Address of server and replace
it in `./remote/production/Caddyfile` and in `Makefile`

```
// ./remote/production/Caddyfile
http://161.35.71.158

// File: ./Makefile
production_host_ip = '161.35.71.158'
```



```bash
make production/deploy/api
```

## Listening to Logs On Production
```bash
sudo journalctl -u api
```

## Useful Development Commands

### Psql Migration Commands
```bash
migrate -path=./migrations -database=$GREENLIGHT_DB_DSN up
```

## TODO
- [ ] remove SMTP credentials hardcode from `main.go` and set as ENV variable
