# racemanagerjson

## getCurses
# Descripción:
Obtiene todas las cursas o solo una indicándole el ID

### Parámetros:
* id (opcional): Filtra rutas por ID y devuelve la que corresponda

### Llamada a la api:
http://[servidor]/api/getCurses/[id si se desea]

### Ejemplo de resultado:
```json
    {
        "curses": [
            {
                "id": 1,
                "nom": "Cursa1",
                "dataInici": "2024-05-25",
                "dataFi": "2024-05-26",
                "lloc": "aaa",
                "esport": {
                    "id": 1,
                    "nom": "Ciclisme"
                },
                "estat": {
                    "id": 1,
                    "nom": "En preparació"
                },
                "descripcio": "asasa",
                "limit": 11,
                "inscrits": 3,
                "foto": "foto",
                "web": "a"
            }
        ],
        "status": {
            "code": "200",
            "description": "Ok"
        }
    }
```

### inscriure
 * request

Envía todos los datos de un participante y el id de una cursa, para registrarlo

 * response

Devuelve un objeto llamado **response** con código de error y descripción del error

### participantCheckpoint
 * request

Envía los id del beacon y del checkpoint, además de un timestamp.

 * response

Devuelve un objeto llamado **response** con código de error y descripción del error

### getCircuits
 * request

Pide todos los cricuitos y opcionalmente de una cursa concreta

 * response

Devuelve todos los circuitos (o el de la ruta indicada) y de cada circuito sus checkpoints
También devuelve un objeto llamado **response** con código de error y descripción del error