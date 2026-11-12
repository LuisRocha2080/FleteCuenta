# Plan de pruebas — FleteCuenta

## Automáticas (Jest)

La lógica de cálculo vive en `src/lib/` y se prueba sin interfaz.

- [ ] Cálculo de utilidad con comisión y anticipo.
- [ ] Liquidación de un mes sin viajes y de un mes con viajes entre dos meses.
- [ ] Guardado de fotos de comprobantes sin conexión.
- [ ] Desactivación de camión con historial.
- [ ] Rendimiento con 2 000 viajes de prueba.

## Manuales en teléfono real

- [ ] Instalación del APK en Android 10 o superior.
- [ ] Uso completo en modo avión.
- [ ] Cierre abrupto de la app y reapertura sin pérdida de datos.
- [ ] Exportación y apertura del archivo en otra app.

## Comandos

```bash
npm test
npx tsc --noEmit
```
