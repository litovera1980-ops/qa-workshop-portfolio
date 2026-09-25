# API Testing — Casos de prueba

## Caso API-01 GET FELIZ

**Objetivo: verificar una mascota existente en el inventario (camino feliz)**

**Operación y endpoint: GET [baseURL/pet/{petId}]**

**Precondiciones: acceso al entorno Swagger Petstore, que exista la mascota con ID válido (id=3) en la base de datos**

**Datos de entrada: https://petstore.swagger.io/v2/pet/3**

**Resultado esperado: código de respuesta 200, muestra los datos de la mascota**

**Resultado obtenido: 200 OK**

**Evidencia: 
![Evidencia API-01]<evidence\api-01 get feliz.png>**

---

## Caso API-02 GET NO FELIZ

**Objetivo: consultar una mascota que no existe en el inventario (camino No feliz)**

**Operación y endpoint: GET [baseURL/pet/{petId}]**

**Precondiciones: acceso al entorno Swagger Petstore, indicar el petId=4 ya que el mismo no existe en la base de datos**

**Datos de entrada: https://petstore.swagger.io/v2/pet/4**

**Resultado esperado: código de respuesta 404 (no se encuentra), mensaje de error que no existe la página**

**Resultado obtenido: 404 Not found, no existe la mascota que se quiere consultar**

**Evidencia:
![Evidencia API-02]<evidence/api-02 get NO feliz.png>**

---

## Caso API-03 POST FELIZ

**Objetivo: verificar la creación exitosa de una nueva mascota**

**Operación y endpoint: POST /pet**

**Precondiciones: acceso al entorno Swagger Petstore, el id=2228 debe estar libre**

**Datos de entrada:
{
  "id": 2228,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "tiranosaurio",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
**

**Resultado esperado: código de respuesta 200 o 201, la mascota debe crearse**

**Resultado obtenido: 200 OK, la mascota fué creada correctamente**

**Evidencia:
![alt text](<api-03 post feliz.png>)**

---

## Caso API-04 POST NO FELIZ

**Objetivo: no permitir crear mascotas con entradas inválidas (código de mascota)**

**Operación y endpoint: POST /pet**

**Precondiciones: acceso al entorno Swagger Petstore, enviar petId con un código no admitido (alfanumérico)**

**Datos de entrada:
{
  "id": 222A,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "tiranosaurio9999999999999999999999999999",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}**

**Resultado esperado: código de error 400 (bad request)**

**Resultado obtenido: código 400, no se pudo grabar la mascota debito al carácter inválido en el petId (A)**

**Evidencia:
![alt text](<api-04 post NO feliz.png>)**
