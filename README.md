# Coturn Admin Instance

Container for executing [turnadmin](https://github.com/coturn/coturn/wiki/turnadmin) commands

## Usage
### To create shared secret
```bash
docker run --rm zolochevska/3dsrelayadmin -e  "<PG_CONNECTION_STRING>" -s <SECRET> -r <REALM>
```

example:
```bash
docker run --rm zolochevska/3dsrelayadmin -e  "host=something.postgres.database.azure.com dbname=coturndb user=coturn@something password=ADecentPassword? connect_timeout=30 sslmode=require port=5432"  -s verySecretSecret -r azturntst.org
```

### To add user
```bash
docker run --rm  $dockerimage -e "<PG_CONNECTION_STRING>" -a -u <USERNAME> -p <PASSWORD> -r <REALM>
```

example:
```bash
docker run --rm zolochevska/3dsrelayadmin -e  "host=something.postgres.database.azure.com dbname=coturndb user=coturn@something password=ADecentPassword? connect_timeout=30 sslmode=require port=5432" -a -u coolUsername -p SomeGoodPassword -r azturntst.org
```
