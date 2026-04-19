# CARSIL Mobile Management System

## Descripcion
Sistema integral de gestion empresarial para entornos moviles diseñado para la compañia CARSIL SAC. La aplicacion permite la administracion de procesos comerciales, control de inventario y gestion de asistencia bajo un esquema de alta seguridad y disponibilidad offline.

## Caracteristicas Principales

### 1. Gestion Comercial y Documentaria
- Generacion automatizada de Proformas y Facturas en formato PDF de alta resolucion.
- Integracion de codigos QR deterministicos para validacion de documentos.
- Sistema de calculo de impuestos (IGV) y subtotales configurables.
- Exportacion directa de documentos al almacenamiento local del dispositivo.

### 2. Seguridad y Proteccion de Datos (SGSI)
- Autenticacion robusta mediante JSON Web Tokens (JWT) gestionados localmente.
- Politica de bloqueo automatico (Lockout Policy) tras intentos fallidos de acceso.
- Validacion mediante reto matematico (CAPTCHA Nativo) para prevencion de ataques automatizados.
- Proteccion contra ingenieria social y malware mediante FLAG_SECURE para evitar capturas de pantalla y grabaciones.
- Politica de No-Backup para prevenir la extraccion de datos sensibles mediante depuracion.

### 3. Gestion Operativa
- Control de Inventario en tiempo real con actualizacion de stock tras ventas.
- Modulo de Asistencia para personal con registro de geolocalizacion y tiempos.
- Control de Acceso Basado en Roles (RBAC) que sincroniza dinamicamente la interfaz segun los permisos del usuario.

## Arquitectura Tecnica

### Stack de Tecnologias
- **Lenguaje:** Kotlin
- **Interfaz de Usuario:** Jetpack Compose (Modern Declarative UI)
- **Persistencia Local:** SQLite con Room Database
- **Base de Datos Remota:** MySQL (Sincronizacion con instancias en Railway)
- **Inyeccion de Dependencias:** Kotlin-based custom providers
- **Procesamiento de PDF:** Android Graphics Engine para renderizado de documentos

### Estructura de Datos
El sistema utiliza un esquema de sincronizacion hibrido que garantiza la operatividad sin conexion a internet, permitiendo la gestion de Clientes, Productos y Documentos Comerciales de forma local y su posterior persistencia en servidores remotos.

## Configuracion e Instalacion

### Requisitos
- Android SDK 24 o superior.
- Android Studio Ladybug o superior.
- Java Development Kit (JDK) 11.

### Pasos
1. Clonar el repositorio.
2. Configurar el archivo `google-services.json` si se integran servicios de Firebase.
3. Actualizar `local.properties` con las rutas del SDK correspondientes.
4. Ejecutar el proyecto mediante Gradle (`./gradlew assembleDebug`).

## Notas de Seguridad
Este proyecto fue diseñado siguiendo estandares de endurecimiento de aplicaciones (Hardening), incluyendo ofuscacion de codigo mediante R8/ProGuard y ocultamiento de secretos de firma de tokens.
