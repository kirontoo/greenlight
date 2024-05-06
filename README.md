# greenlight

Greenlight is a project covered in the book `Let's Go Further`
by Alex Edwards.


ENV VARIABLES:

export GREENLIGHT_DB_DSN="postgres://greenlight:password@localhost/greenlight"

## Migration Commands
```bash
migrate -path=./migrations -database=$GREENLIGHT_DB_DSN up
```

