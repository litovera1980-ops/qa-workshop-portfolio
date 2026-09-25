# API Testing — Casos de prueba

## Caso API-01 GET FELIZ

**Objetivo: verificar una mascota existente en el inventario (camino feliz)**

**Operación y endpoint: GET [baseURL/pet/{petId}]**

**Precondiciones: acceso al entorno Swagger Petstore, que exista la mascota con ID válido (id=3) en la base de datos**

**Datos de entrada: https://petstore.swagger.io/v2/pet/3**

**Resultado esperado: código de respuesta 200, muestra los datos de la mascota**

**Resultado obtenido: 200 OK**

**Evidencia:
![Evidencia Api01](evidence/api-01%20get%20feliz.png)

---

## Caso API-02 GET NO FELIZ

**Objetivo: consultar una mascota que no existe en el inventario (camino No feliz)**

**Operación y endpoint: GET [baseURL/pet/{petId}]**

**Precondiciones: acceso al entorno Swagger Petstore, indicar el petId=4 ya que el mismo no existe en la base de datos**

**Datos de entrada: https://petstore.swagger.io/v2/pet/4**

**Resultado esperado: código de respuesta 404 (no se encuentra), mensaje de error que no existe la página**

**Resultado obtenido: 404 Not found, no existe la mascota que se quiere consultar**

**Evidencia:
![Evidencia Api02](evidence/api-02%20get%20NO%20feliz.png)

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
![Evidencia Api03](evidence/api-03%20post%20feliz.png)


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
![Evidencia Api04](evidence/api-04%20post%20NO%20feliz.png)



# Conclusiones

## Resultados relevantes
- Consistencia de datos al no permitir la carga de datos inválidos (caracteres alfanuméricos), se evita corrupción en el ID de las mascotas.
- En ambos casos felices, los resultados demostraron consistencia al responder correctamente según lo que se esperaba.

## Limitaciones
- Funcionalidades críticas, compra con usuario registrado y compra sin registrarse.
- Opción de búsqueda.
- Inventario completo de mascotas.
- Estructura de la página y creación de nueva sección de productos.


## Pruebas adicionales
De contar con mas tiempo, automatizaría y ampliaría las pruebas utilizando Playwright, esto ayudaría a poder abarcar los puntos que quedaron pendientes ya citados en el item anterior "Limitaciones"
Adicionalmente se podrían incluir pruebas de:
 - Validación de stock
 - Anulación de pedidos
 - Varios métodos de pago
 - Métodos de retiro (en tienda, envío por courier)

