# Introducción a Amazon CloudFront

**Amazon CloudFront** es un servicio de red de entrega de contenido (CDN) que permite distribuir contenido estático y dinámico globalmente con baja latencia y alta velocidad de transferencia.

## ¿Por qué usar CloudFront?

Cuando alojamos archivos en S3, estos se almacenan en una región específica. Si usuarios acceden desde regiones lejanas, pueden experimentar **alta latencia**. CloudFront resuelve esto con:

- Entrega de contenido desde la **edge más cercana** al usuario.
- **Cacheo** de contenido para acelerar futuras solicitudes.

## Ventajas

- 🔥 **Reducción de latencia**: menor tiempo de carga gracias al uso de edge locations.
- 💸 **Ahorro en costos de transferencia** desde S3 hacia CloudFront.
- 🧠 **Cacheo inteligente**: con opciones para invalidar contenido o definir políticas de caché.
- 🌍 **Cobertura global** con edge locations distribuidas.
- 🔒 **Seguridad integrada** contra ataques DDoS y acceso restringido por región.


## Casos de uso

- Distribución global de páginas web estáticas (hosted en S3).
- Aceleración de descargas y cargas de archivos.
- Protección contra accesos directos a S3 (mediante Origin Access Identity).
- Control granular del comportamiento de la caché.
- Implementación de políticas de acceso geográficas.

## Configuración básica

1. **Crear una distribución** de CloudFront.
2. Seleccionar como origen un bucket S3, una instancia EC2 o un Load Balancer.
3. Configurar compresión, políticas de caché, redirección HTTPS, etc.
4. (Opcional) Asignar un **dominio personalizado** con certificado SSL.
5. Establecer el **index.html** como objeto raíz.
6. **Invalidar la caché** cuando se actualice contenido si no se versionan los archivos.

## Política de caché (TTL)

- `minTTL`, `defaultTTL` y `maxTTL`: definen cuánto tiempo los objetos estarán cacheados en los edge locations.
- Se pueden invalidar objetos manualmente o usar estrategias como:
  - Versionado de archivos (React build: `main.abc123.js`).
  - Uso de `Cache-Control` en metadatos para definir expiración en navegador y servidor.

## Seguridad

- Uso de **Origin Access Identity (OAI)** para evitar acceso directo a S3.
- Restricciones por país.
- Integración con **WAF (Web Application Firewall)** para reglas avanzadas.
- Redirección de errores a páginas personalizadas.

## Buenas prácticas

- 🧩 Usar **versionado de archivos** en archivos estáticos.
- 🔄 Invalidar caché solo si es necesario (por límite de 1000 gratuitas).
- 🛡️ Restringir acceso a S3 solo a través de CloudFront (OAI).
- 🧠 Configurar correctamente `Cache-Control` y `Expires`.