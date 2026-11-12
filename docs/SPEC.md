# Especificación — FleteCuenta

Requisitos escritos con el patrón EARS («Cuando…, el sistema deberá…»). Cada uno es verificable con una prueba (ver [PRUEBAS.md](PRUEBAS.md)).

## Alcance de la versión 1.0

Control de viajes de carga: flete cobrado, gastos de ruta y utilidad por viaje y por camión. Funciona en un solo dispositivo, sin cuentas de usuario y sin servidor.

## Requisitos funcionales

| ID | Requisito |
|---|---|
| R01 | Cuando se guarda un viaje, el sistema deberá exigir camión, origen, destino y flete mayor a cero. |
| R02 | Cuando se registra un gasto, el sistema deberá asociarlo al viaje y actualizar la utilidad del viaje de inmediato. |
| R03 | El sistema deberá calcular la utilidad de un viaje como flete menos la suma de sus gastos y la comisión del chofer. |
| R04 | Cuando un cobro supera su fecha de vencimiento sin registrarse como cobrado, el sistema deberá marcarlo como vencido. |
| R05 | Cuando el usuario elige un mes y un camión, el sistema deberá generar la liquidación en PDF con viajes, gastos y utilidad. |
| R06 | Si el usuario adjunta una foto de comprobante, el sistema deberá guardarla en el dispositivo y no subirla a ningún servidor. |
| R07 | Mientras el viaje esté en ruta, el sistema deberá permitir registrar gastos sin conexión. |
| R08 | Cuando se elimina un camión con viajes registrados, el sistema deberá desactivarlo en vez de borrar su historial. |

## Requisitos no funcionales

| ID | Requisito |
|---|---|
| N01 | La app deberá abrir en menos de 3 segundos en un teléfono Android de gama baja (2 GB de RAM). |
| N02 | Todos los datos deberán almacenarse en SQLite local y no enviarse a ningún servidor. |
| N03 | La interfaz deberá estar en español con montos en bolivianos (Bs) y fechas dd/mm/aaaa. |
| N04 | Los botones táctiles deberán medir al menos 48 dp. |
| N05 | La app deberá operar completa sin conexión a internet. |
| N06 | El costo de licencias de cualquier dependencia deberá ser cero. |

## Fuera de alcance (v1.0)

- Sin seguimiento GPS del camión: no es un sistema de rastreo.
- Un solo dispositivo por flota en la primera versión.
- No emite carta de porte ni documentos aduaneros.

## Criterios de aceptación globales

1. Un usuario nuevo registra su primer dato útil en menos de 5 minutos.
2. Ningún dato se pierde al cerrar la app de forma abrupta.
3. Los totales coinciden con un cálculo manual en los casos de prueba de [PRUEBAS.md](PRUEBAS.md).
