
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

##### Response:
    Code: 200
    Content: 
    {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6ImFkMjEwNDBAYS5jb20iLCJuYmYiOjE2OTc0ODc3MzIsImV4cCI6MTY5NzQ4OTUzMiwiaWF0IjoxNjk3NDg3NzMyfQ._mx7fdGe9AhnAoRMu3i6f25cxdjF_sdlu7an0bAqj_Q",
        "token_aora": "720dd723-e594-41e7-b948-d6a5ed37439bcecjocdhqqbyzcytmcmtpykxxclkectufutxthydtphvtctmqwjspebdufmmqtdnwgteibaedizaroeviztisafatqcovmnamuzm973469296313-2698-4176-8a38-80f4d5cd2da029442938-4cf9-4f5a-9896-3dc5cfc5a0ed"
    }


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

#### Response
    Code: 200
    Content: 
    {
        "error": false,
        "msg": "Creación correcta.",
        "finalizado": false,
        "topico_id": 0
    }
#### Error Response
    Code: 401 Unauthorized
    Content: 
    {
        "error": true,
        "msg": "Tipo de identificación no es válido"
    }
## Listar Partner

##### Obtiene el listado de los partners.

| Header |  Descripción                | Requerido                |
| :-------- | :------------------------- |:------------------------- |
| `aoratoken` |  Es el token del usuario | Si |

| Bearer | Descripción                |Requerido                |
| :-------- |  :------------------------- |:------------------------- |
| `token` | Es la autenticación de tipo Bearer para el uso de cada Api |Si |

##### El Api del Registro del Partner es:
```http
  GET /v1/partner/obtiene
```
#### Response
    Code: 200
    Content: 
    [
        {
            "partnerId": 1,
            "nombre": "partner X",
            "direccion": "direccion X",
            "identificacion": "identificacion X",
            "tipo_identificacion": "CEDULA",
            "fecha_Creacion": "11/10/2023 16:39",
            "tokenAuthorization": "2DvR61rXVjg2JnYiSx1xNz1u6tjuXLOxTon7L2dZvB01I1DHdqRPg9FDLBVNR7AKUtjeAaXaUbCM8AlEpcQr39RTijwJgPHxAqgZ"
        },
        {
            "partnerId": 2,
            "nombre": "partner XY",
            "direccion": "direccion XY",
            "identificacion": "identificacion XY",
            "tipo_identificacion": "RUC",
            "fecha_Creacion": "16/10/2023 17:37",
            "tokenAuthorization": "4D5ESOBwsoMejPdVGDCndciZ7qMdpizyl8YkKo0hUbK4yVuME8amEA8cegGmBhHJzY2l02LcMeTBRnkm5AZqIMukA6GnhOgwUBFa
    "
        }
    ]

#### Error Response
    Code: 401 Unauthorized
    Content: 
    {
        "error": true,
        "msg": "Token Inválido"
    }

## Listar Categorías

##### Obtiene listado de las categorías.

| Header |  Descripción                | Requerido                |
| :-------- | :------------------------- |:------------------------- |
| `aoratoken` |  Es el token del usuario | Si |

| Bearer | Descripción                |Requerido                |
| :-------- |  :------------------------- |:------------------------- |
| `token` | Es la autenticación de tipo Bearer para el uso de cada Api |Si |

##### El Api de Listar Categorías es:
```http
  GET /v1/categorias/agrupada
```
#### Response
    Code: 200
    Content: 
    {
        "categorias": [
            {
                "categoriaId": 48,
                "descripcion": " ",
                "titulo": "SERVICIOS MÁS PEDIDOSs",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/ffd1a0ae-7c31-4147-bfc5-d1a1d0ce41d9.jpg"
            },
            {
                "categoriaId": 36,
                "descripcion": "ELECTRICIDAD GASFITERÍA CERRAJERÍA ALBAÑILERÍA CARPINTERÍA LIMPIEZA OTRO",
                "titulo": "HOGAR Y OFICINA",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/fb7355d9-c7eb-4cca-9bfc-451ee50f0d62.jpg"
            },
            {
                "categoriaId": 37,
                "descripcion": "AIRE ACONDICIONADO LAVADORA SECADORA COCINA REFRIGERADORA HORNO",
                "titulo": "ELECTRODOMÉSTICOS",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/3e280a50-15e3-4ff4-8d0c-59fe975d2172.jpg"
            },
            {
                "categoriaId": 38,
                "descripcion": "CASA INTELIGENTE INTERNET COMPUTADORAS IMPRESORAS TV",
                "titulo": "TECNOLOGÍA",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/28f074d2-d9d1-4e66-9650-516290b98522.jpg"
            },
            {
                "categoriaId": 50,
                "descripcion": "sdsd",
                "titulo": "PRuebas",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/ba1a3ebf-9d42-4f9f-b45a-1bae0ff5e810.jpg"
            },
            {
                "categoriaId": 40,
                "descripcion": " ",
                "titulo": "CASAS COMERCIALES",
                "empresa": true,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/d6dbd481-d9b3-48fc-bb1a-f6bc67e2d97c.jpg"
            },
            {
                "categoriaId": 39,
                "descripcion": "LUBRICACIÓN BATERÍA CERRAJERÍA",
                "titulo": "VEHÍCULOS",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/7e6fa13b-984b-439f-946f-251f9d3a6e01.jpg"
            }
        ]
    }


#### Error Response
    Code: 401 Unauthorized
    Content: 
    {
        "error": true,
        "msg": "Token Inválido"
    }

## Creación de invitado b2bc

##### Crea el invitado cuando accede por primera vez a la web.

| Header |  Descripción                | Requerido                |
| :-------- | :------------------------- |:------------------------- |
| `aoratoken` |  Es el token del usuario | Si |

| Bearer | Descripción                |Requerido                |
| :-------- |  :------------------------- |:------------------------- |
| `token` | Es la autenticación de tipo Bearer para el uso de cada Api |Si |

##### El Api de v1/clienteb2bc/invitado es:
```http
  POST /v1/clienteb2bc/invitado
```
 Parámetro | Tipo     | Descripción                |Requerido                |
| :-------- | :------- | :------------------------- |:------------------------- |
| so | string  |  El sistema operativo que está usando, en este caso se enviaría WEB |Si |
| namedevice | string  | Se obtiene la descripción del dispositivo |Si |
| tokendevice | long  | El tokendevice obtenido por firebase |Si |
| tokenpartner | long  | Este token es del api Listar Partners, con este token se relaciona el cliente a que partner está relacionado |Si |

#### Response
    Code: 200
    Content: 
    {
        "categorias": [
            {
                "categoriaId": 48,
                "descripcion": " ",
                "titulo": "SERVICIOS MÁS PEDIDOSs",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/ffd1a0ae-7c31-4147-bfc5-d1a1d0ce41d9.jpg"
            },
            {
                "categoriaId": 36,
                "descripcion": "ELECTRICIDAD GASFITERÍA CERRAJERÍA ALBAÑILERÍA CARPINTERÍA LIMPIEZA OTRO",
                "titulo": "HOGAR Y OFICINA",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/fb7355d9-c7eb-4cca-9bfc-451ee50f0d62.jpg"
            },
            {
                "categoriaId": 37,
                "descripcion": "AIRE ACONDICIONADO LAVADORA SECADORA COCINA REFRIGERADORA HORNO",
                "titulo": "ELECTRODOMÉSTICOS",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/3e280a50-15e3-4ff4-8d0c-59fe975d2172.jpg"
            },
            {
                "categoriaId": 38,
                "descripcion": "CASA INTELIGENTE INTERNET COMPUTADORAS IMPRESORAS TV",
                "titulo": "TECNOLOGÍA",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/28f074d2-d9d1-4e66-9650-516290b98522.jpg"
            },
            {
                "categoriaId": 50,
                "descripcion": "sdsd",
                "titulo": "PRuebas",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/ba1a3ebf-9d42-4f9f-b45a-1bae0ff5e810.jpg"
            },
            {
                "categoriaId": 40,
                "descripcion": " ",
                "titulo": "CASAS COMERCIALES",
                "empresa": true,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/d6dbd481-d9b3-48fc-bb1a-f6bc67e2d97c.jpg"
            },
            {
                "categoriaId": 39,
                "descripcion": "LUBRICACIÓN BATERÍA CERRAJERÍA",
                "titulo": "VEHÍCULOS",
                "empresa": false,
                "ruta": "http://testingecb2bc.aoraservicios.com//images/core/7e6fa13b-984b-439f-946f-251f9d3a6e01.jpg"
            }
        ]
    }


#### Error Response
    Code: 401 Unauthorized
    Content: 
    {
        "error": true,
        "msg": "Token Inválido"
    }







![Logo](http://webprod.aoraservicios.com//images/core/407e82ac-126d-4dbc-a4b4-657a92965cd5.jpg)


