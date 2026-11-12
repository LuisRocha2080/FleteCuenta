# Modelo de datos — FleteCuenta

Base SQLite local (`expo-sqlite`). Fechas en formato ISO `AAAA-MM-DD`; montos en bolivianos con dos decimales (guardados como enteros en centavos).

## `camiones`

Columnas: id, placa, descripcion, capacidad_t, activo

## `choferes`

Columnas: id, nombre, telefono, comision_pct

## `viajes`

Columnas: id, camion_id, chofer_id, origen, destino, fecha_salida, fecha_llegada, km, flete, anticipo, estado

## `gastos_viaje`

Columnas: id, viaje_id, categoria, monto, fecha, nota, foto_uri

## `cobros`

Columnas: id, viaje_id, cliente, monto, vence_en, cobrado_en

## Reglas generales

- Cada tabla tiene `id` entero autoincremental.
- Los borrados con historial son **lógicos** (campo `activo`) para no romper reportes.
- Cambios de esquema mediante migraciones numeradas en `src/db/migraciones/`.
