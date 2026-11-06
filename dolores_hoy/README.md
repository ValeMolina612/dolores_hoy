# Dolores Hoy

Tablero Flutter que consume 5 APIs gratuitas (Open-Meteo, Frankfurter, Nager.Date,
Wikipedia y NASA APOD) con buenas prácticas de seguridad. Hecho con TDD.
Desarrollo Móvil Integral · UTNG · Prof. Anastacio Rodríguez García.

## Cómo arrancarlo (VS Code)

1. Abre esta carpeta en VS Code.
2. En la terminal, genera las carpetas de plataforma (android/, ios/, etc.). No pisa lo que ya existe:
   ```
   flutter create . --project-name dolores_hoy
   ```
3. Instala dependencias:
   ```
   flutter pub get
   ```
4. Corre las pruebas (no necesitan internet):
   ```
   flutter test
   ```
5. Ejecuta la app con la clave de la NASA:
   ```
   flutter run --dart-define-from-file=secrets.json
   ```
   `secrets.json` trae `DEMO_KEY`. Para mejor límite, pide tu clave gratis en https://api.nasa.gov
   y pégala ahí. **secrets.json está en .gitignore: no lo subas.**

## Estructura

- `lib/dominio/` errores seguros y modelos
- `lib/datos/` ClienteSeguro (única puerta a internet), ConfigClaves y un servicio por API
- `lib/presentacion/` ViewModel y pantalla
- `test/` pruebas de cliente, servicios, seguridad y tablero
