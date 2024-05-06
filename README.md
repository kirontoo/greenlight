# greenlight

Greenlight is a project covered in the book `Let's Go Further`
by Alex Edwards.

I've also made a series of blog posts as I follow along this book, check it out
at [blog.amyndang.me](https://blog.amyndang.me/series/learning%20the%20backend/)


## ENV VARIABLES:
```bash
export GREENLIGHT_DB_DSN="postgres://greenlight:password@localhost/greenlight"
```

## Migration Commands
```bash
migrate -path=./migrations -database=$GREENLIGHT_DB_DSN up
```

