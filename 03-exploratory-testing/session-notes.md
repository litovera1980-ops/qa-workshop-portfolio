# Sesión 1

## Charter 2
**Título:** (R5) Datos o fotos desactualizadas en el catálogo de productos.
**Misión:** Explorar el catálogo de productos y las páginas.
            usando el menú de categorias disponible (fish, dogs, reptiles, cats, birds).
            para identificar inconsistencias de datos, imagenes u omisiones de productos o servicios ofrecidos.
**Área principal explorada:** Exposición clara y precisa de productos ofrecidos.

## ÁREAS
- Plataforma JpetStore
- https://petstore.octoperf.com/actions/Catalog.action
- Navegador Chrome / SO Windows 11

## INICIO
16/09/2026 - 21:00hs
30 minutos

## TESTER
Victor Vera

## DESGLOSE DE TAREAS
- Diseño de pruebas: 17% (5 minutos).
- Exploración: 66% (20 minutos).
- Reporte de hallazgos: 17% (5 minutos).

## ARCHIVOS DE DATOS
Apuntes/información proveída por el administrador de la tienda en cuanto al inventario de mascotas y accesorios comercializados por la misma.

## NOTAS DE PRUEBA
- No se encontraron en las categorias exploradas accesorios para mascotas que son comercializados por la tienda.
- Se pudo constatar que la mayoría de los productos poseen imágenes genéricas que no representan al verdadero producto.

## LISTA DE RIESGOS
Riesgo R5: datos imprecisos la presencia de imágenes rotas, genéricas o descripciones imprecisas en las mascotas puede generar desconfianza en el usuario o llevar a la cancelación de pedidos al no recibir el producto visualizado.

## DEFECTOS (BUGS)
BUG-R5-01: misma imagen para todas las razas de perros en la categoría "Dogs" (razas completamente distintas).

BUG-R5-02: descripción incompleta en la categoría "Fish" (falta información como requerimientos del espécimen).

## INCIDENTES (ISSUES)
¿Existe un repositorio u opción donde el equipo de catálogo pueda actualizar las imágenes y descripciones de forma dinámica sin depender de un despliegue de código?
