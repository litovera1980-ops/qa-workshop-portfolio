# API Testing — Alcance

## API
Swagger Petstore

## Alcance funcional
Gestión de mascotas (pet).

## Operaciones seleccionadas

| Método HTTP | Endpoint     | Propósito |
|-------------|--------------|-----------|
| GET         | /pet/{petId} | Obtener todos los productos/mascotas disponibles   |
| POST        | /pet         | Probar la publicación de nuevos productos/mascotas |

## Justificación
Ambos métodos constituyen a los de mayor impacto en la operativa de la tienda, al ser el primero pruebas de consulta sobre el inventario existente (productos que se ofrecen) y el segundo nos ayudará a probar la publicación de nuevos productos o mascotas.

## Condiciones de prueba identificadas
Se estará verificando para cada operación:
 * Camino Feliz
   GET --> obtener una mascota que existe en el inventario.
   POST --> grabar un producto con la estructura de datos correcta.
   
* Camino no feliz
   GET --> consultar un id de mascota que no existe en el inventario.
   POST --> intentar grabar un producto con un "id" ya existente.

## Fuera de alcance
Quedará fuera del alcance de las pruebas: "store" (pedidos de la tienda) y "user" (operaciones sobre el usuario), además las operaciones de PUT y DELETE en "pet" (gestión de mascotas).
