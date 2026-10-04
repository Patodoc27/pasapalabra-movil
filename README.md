# Pasapalabra Móvil 🎮

Versión personal de **Pasapalabra Bio** adaptada para celular, para práctica individual contra Boti.

## Jugar

**Opción 1 — En el navegador:** abrir `index.html` en el celular (bajando el archivo o por GitHub Pages).

**Opción 2 — App instalada:** descargar el APK desde la sección **Releases**.

## Características

- Solo modo contra **Boti** (sin multijugador ni ranking en línea — nada sale del teléfono)
- Tiempos de **5 u 8 minutos**
- **20 roscos** pre-armados del banco de ~99 términos, con consignas "empieza por" y "contiene la" (letras intermedias)
- Progreso personal guardado en el teléfono (rondas, aciertos, conceptos pendientes de repaso)
- Botón **↻ Repasar** para practicar solo las palabras que costaron
- Lectura de consignas en voz alta (botón 📖): dice la consigna, pausa de 2 segundos y lee la definición
- Boti espera 6–7 segundos antes de escribir su respuesta
- Funciona 100% offline una vez abierto

## Estructura

- `index.html` — el juego completo, autocontenido (HTML + CSS + JS en un solo archivo)
- `android/` — proyecto fuente del APK (WebView wrapper: `AndroidManifest.xml`, `src/`, `res/`, `assets/`)

## Recompilar el APK

Con Android SDK instalado (aapt2, zipalign, apksigner de build-tools):

```bash
cp index.html android/assets/index.html
aapt2 link -o build/app.apk -I $ANDROID_HOME/platforms/android-35/android.jar \
  --manifest android/AndroidManifest.xml -A android/assets
# agregar dex/classes.dex, zipalign y firmar con tu keystore
```

Basado en [pasapalabra-bio](https://github.com/Patodoc27/pasapalabra-bio) de Patricia Inés Castro.
