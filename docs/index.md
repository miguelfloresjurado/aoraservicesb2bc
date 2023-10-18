
# Apis b2bc

Proyecto de integración con las distintas compañías con el fin de integrarse


## Autenticación del Partner

##### Todo acceso a las APIs es necesario iniciar sesión previamente con las credenciales previamente dadas al partner.

##### Permite iniciar sesión y obtener credenciales de acceso a nivel de Header y Authorization que se utilizan en las demás APIs.

| Header |  Descripción                | Requerido                |
| :-------- | :------------------------- |:------------------------- |
| `aoratoken` |  Es el token del usuario | Si |

| Bearer | Descripción                |Requerido                |
| :-------- |  :------------------------- |:------------------------- |
| `token` | Es la autenticación de tipo Bearer para el uso de cada Api |Si |

##### El Api del Login es:
```http
  POST /api/auth/login
```

| Parámetro | Tipo     | Descripción                |Requerido                |
| :-------- | :------- | :------------------------- |:------------------------- |
| Username | string | El nombre del usuario asignado para acceder al token |Si |
| Password | string | La clave asignada para acceder a la plataforma |Si |


## Registro de Partner

##### Crear nuevo partner.

| Header |  Descripción                | Requerido                |
| :-------- | :------------------------- |:------------------------- |
| `aoratoken` |  Es el token del usuario | Si |

| Bearer | Descripción                |Requerido                |
| :-------- |  :------------------------- |:------------------------- |
| `token` | Es la autenticación de tipo Bearer para el uso de cada Api |Si |

##### El Api del Registro del Partner es:
```http
  POST /v1/partner
```

| Parámetro | Tipo     | Descripción                |Requerido                |
| :-------- | :------- | :------------------------- |:------------------------- |
| nombre | string  |  El nombre del partner |Si |
| direccion | string  | La dirección del partner |Si |
| tipo_identificacion_id | long  | El Id para el registro del id correspondiente al catálogo **"TIPO DOCUMENTO"** |Si |





![Logo](http://webprod.aoraservicios.com//images/core/407e82ac-126d-4dbc-a4b4-657a92965cd5.jpg)


