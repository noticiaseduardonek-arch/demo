# Control de Lecturas — app Android

Es la misma app (Lecturas de Medidores, Retrolavado y Cloro y pH) convertida para funcionar sin servidor
dentro de un APK. Los datos se guardan en el teléfono (almacenamiento local de la app).

## Opción A: obtener el APK con GitHub (no necesita Android Studio)
1. Crea un repositorio en GitHub y sube TODO el contenido de esta carpeta (incluida `.github`).
2. Entra a la pestaña **Actions** → "Construir APK" (se ejecuta solo al subir; si no, botón "Run workflow").
3. Cuando termine (unos 5-8 min), abre la ejecución y descarga `control-lecturas-apk` → contiene `app-debug.apk`.
4. Pásalo al teléfono, ábrelo y permite "Instalar apps de origen desconocido" si lo pide.

## Opción B: con Android Studio
```
npm install
npm run css
npx cap add android
npx cap sync android
npx cap open android      # Build > Build APK(s)
```

## Notas
- La generación automática diaria (después de las 7:00 AM) ocurre al abrir la app. Un APK no puede
  ejecutarse solo en segundo plano; si un día no se abre, ese día no se genera.
- Los datos viven en el teléfono: si desinstalas la app o borras sus datos, se pierden.
- Para modificar la app: edita `www/index.html` / `www/app.js` y vuelve a compilar.
