# GPS Map App en Android 📍
[![Platform](https://img.shields.io/badge/Platform-Android-green.svg)](https://www.android.com)

`GPS Map App` es una aplicación nativa de Android simple que demuestra cómo integrar Google Maps para obtener y mostrar la ubicación GPS actual del usuario en tiempo real.

## 📱 Captura de Pantalla
![App Screenshot](https://github.com/Matias-Bravo-21/AndroidGps/blob/master/pruebas/Captura%20de%20pantalla_2025-10-19_15-48-19.png)

## ✨ Características
* Solicitud de permisos de ubicación en tiempo real (`ACCESS_FINE_LOCATION`).
* Solicitud de permiso de `INTERNET`.
* Integración completa del **Google Maps SDK for Android**.
* Uso de `FusedLocationProviderClient` para obtener la última ubicación conocida del dispositivo de forma eficiente.
* Centrado automático del mapa en la ubicación del usuario.
* Adición de un marcador (`Marker`) en la ubicación actual.

## 🛠️ Tecnologías Utilizadas
* Android Nativo (Java)
* Google Maps SDK
* Google Play Services (Location)
* `FusedLocationProviderClient`

---

## 🚀 Cómo Empezar

Sigue estos pasos para clonar, configurar y ejecutar el proyecto.

### 1. Configuración ObligatorIA: API Key de Google Maps

Este proyecto **no funcionará** si no proporcionas tu propia clave de API de Google Maps.

1.  **Obtén tu API Key:**
    * Ve a la [Google Cloud Console](https://console.cloud.google.com/).
    * Crea un nuevo proyecto o selecciona uno existente.
    * En el menú lateral, ve a "APIs y Servicios" > "Biblioteca".
    * Busca y **habilita** la API **"Maps SDK for Android"**.
    * Asegúrate de que la **Facturación** esté activada para tu proyecto.
    * Ve a "APIs y Servicios" > "Credenciales".
    * Haz clic en "Crear Credenciales" > "API Key".

2.  **Restringe tu Clave (¡Muy Importante!):**
    Para evitar que otros usen tu clave y te generen costos, debes restringirla:
    * En la lista de credenciales, haz clic en tu nueva clave.
    * Bajo "Application restrictions", selecciona **"Android apps"**.
    * Haz clic en "Add an item" y añade las dos cosas que te pide:
        * **Package name:** `com.example.gpsmapapp` (Este debe ser exacto al de tu `AndroidManifest.xml`)
        * **SHA-1 certificate fingerprint:** Abre una terminal en Android Studio y ejecuta `./gradlew signingReport`. Copia la huella `SHA-1` de la variante `debug`.

3.  **Agrega la Clave al Proyecto:**
    * En el proyecto, navega a `app/src/main/res/values/`.
    * Abre el archivo `Maps_api.xml`. (Si no existe, créalo).
    * Pega el siguiente código, reemplazando `TU_API_KEY_AQUI` con la clave que generaste en el paso 1.

    ```xml
    <resources>
        <string name="google_maps_key" translatable="false">TU_API_KEY_AQUI</string>
    </resources>
    ```

### 2. Ejecución

Una vez configurada la API key, ejecutar la app es muy sencillo:

1.  **Clona el Repositorio:**
    ```bash
    git clone https://github.com/Matias-Bravo-21/AndroidGps.git
    ```
2.  **Abre en Android Studio:**
    * Inicia Android Studio.
    * Selecciona "Open" (Abrir).
    * Navega a la carpeta donde clonaste el repositorio y selecciónala.
3.  **Sincroniza Gradle:**
    * Espera a que Android Studio descargue todas las dependencias (como `play-services-maps`).
4.  **Ejecuta la App:**
    * Selecciona un emulador que tenga los servicios de Google Play o conecta un dispositivo Android físico.
    * Presiona el botón "Run" (▶) en la barra de herramientas.

¡Listo! La aplicación debería iniciarse, pedirte permiso de ubicación y luego mostrar el mapa centrado en tu posición actual.
