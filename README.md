# racemanagerjson

## getCurses

### Descripción:
Obtiene todas las cursas o solo una si se indica el ID

### Parámetros:
* (int) - [opcional]: Filtra rutas por ID y devuelve la que corresponda

### Llamada a la api:
http://[servidor]/api/getCurses/[int?]

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
    },
    {
      "id": 2,
      "nom": "Test cursa",
      "dataInici": "2024-05-18",
      "dataFi": "2024-05-26",
      "lloc": "Igualada",
      "esport": {
        "id": 2,
        "nom": "Running"
      },
      "estat": {
        "id": 1,
        "nom": "En preparació"
      },
      "descripcio": "Descripcio test",
      "limit": 1000,
      "inscrits": 3,
      "foto": "foto",
      "web": "website.com"
    }
  ],
  "status": {
    "code": "200",
    "description": "Ok"
  }
}
```

## getCircuits

### Descripción:
Obtiene todos los circuitos o solo uno si se indica el ID

### Parámetros:
* (int) - [opcional]: Filtra los circuitos por la cursa a la que pertenecen

### Llamada a la api:
http://[servidor]/api/getCIRCUITS/[int?]


### Ejemplo de resultado:
```json
{
  "circuits": [
    {
      "id": 1,
      "cursaId": 1,
      "num": 1,
      "distancia": "112.00",
      "nom": "2222",
      "preu": "22.0000",
      "temps": "2024-05-01",
      "checkpoints": [
        {
          "id": 1,
          "pk": null
        }
      ],
      "categories": [
        {
          "id": 1,
          "nom": "cadet"
        }
      ]
    },
    {
      "id": 2,
      "cursaId": 2,
      "num": 3,
      "distancia": "111.00",
      "nom": "Nomrbe",
      "preu": "12.0000",
      "temps": "2024-05-09",
      "checkpoints": [
        {
          "id": 2,
          "pk": "12.00"
        },
        {
          "id": 3,
          "pk": "14.00"
        },
        {
          "id": 4,
          "pk": "18.00"
        }
      ],
      "categories": [
        {
          "id": 5,
          "nom": "Casual"
        },
        {
          "id": 6,
          "nom": "Profesional"
        }
      ]
    }
  ],
  "status": {
    "code": "200",
    "description": "Ok"
  }
}
```

## inscriure

### Descripción:
Inscribe un participante 

### Parámetros:
* (json) - [obligatorio]: Un json que contiene los datos del participante + los id de cur, cir y ccc al que se apunta

Contenido necesario en el json:
```json
{
	"participant": {
		"nif": "44445555D",
		"nom": "David Cano",
		"cognoms": "Cano",
		"dataNaixement": "10-10-2010",
		"telefon": "600655301",
		"email": "dcano@milaifontanals.org",
		"esFederat": 0
	},
	"cursaId": 1,
	"circuitId": 1,
	"catId": 1
}
```

### Llamada a la api:
http://[servidor]/api/inscriure/[json]


## participantCheckpoint

### Descripción:
Registra que un participante ha pasado por un checkpoint

### Parámetros:
* (json) - [obligatorio]: Un json que contiene los id de par, ccc, ea y chk ademas del tiempo

Contenido necesario en el json:
```json
{
    "parId": 1,
    "cccId": 1,
    "beaId": 1,
    "chkId": 3,
    "temps": "2011-02-03"
}
```

### Llamada a la api:
http://[servidor]/api/participantCheckpoint/[json]
