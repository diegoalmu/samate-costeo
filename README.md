# Samate — Costeo & Precios

Herramienta web de una sola página (`index.html`) para calcular el costo de una receta o producto (ingredientes, costos indirectos, tiempo y margen) y sugerir el precio de venta por canal (venta directa, plataformas con comisión, etc.), incluyendo el IVA sobre comisión.

Los datos de sesión del usuario (recetas guardadas, historial) se guardan en Firebase (Authentication + Firestore) bajo su propia cuenta.

## Qué hace

- Calcula el costo total por unidad a partir de ingredientes, cantidades usadas y costos de paquete.
- Suma costos indirectos, tiempo de trabajo y margen deseado.
- Sugiere el precio de venta directa y el precio ajustado por canal (según la comisión de cada plataforma).
- Permite iniciar sesión (Firebase Auth) para guardar y recuperar tus recetas.

## Cómo instalarlo / usarlo

No requiere build ni servidor: es un único archivo HTML.

1. Descarga o clona el repositorio.
2. Abre `index.html` directamente en tu navegador, o sírvelo con cualquier servidor estático:

   ```bash
   npx serve .
   ```

## Configuración

El proyecto usa Firebase (Auth + Firestore) para guardar los datos del usuario. La configuración del proyecto de Firebase (`firebaseConfig`) está incluida directamente en `index.html`, ya que es una app estática sin proceso de build.

Si quieres usar tu propio proyecto de Firebase:

1. Crea un proyecto en [Firebase Console](https://console.firebase.google.com/).
2. Habilita **Authentication** y **Firestore**.
3. Reemplaza el objeto `firebaseConfig` en `index.html` con el de tu propio proyecto.
4. Configura las reglas de seguridad de Firestore para restringir el acceso a cada usuario a sus propios datos.

> Nota: las claves dentro de `firebaseConfig` (apiKey, projectId, etc.) son identificadores públicos del lado del cliente, no credenciales secretas; la seguridad real depende de las reglas de Firestore/Auth del proyecto.

## Licencia

Este proyecto no incluye una licencia de código abierto (ver nota en la auditoría del repositorio).
