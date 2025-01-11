# Proyecto de Gestión de Archivos en Servicios de Almacenamiento

Este proyecto proporciona una implementación basada en el patrón Strategy para gestionar archivos en servicios de almacenamiento como MinIO, S3, entre otros, utilizando Go.

## Estructura del Proyecto

- `bucket.go`: Define la interfaz `Strategy` y la estructura `Context` para la descarga de archivos.
- `minio.go`: Implementa la estrategia de descarga de archivos desde MinIO.
- `go.mod` y `go.sum`: Archivos de gestión de dependencias de Go.
- `LICENSE`: Licencia del proyecto.

## Uso

### Crear un Cliente MinIO

Para crear un cliente MinIO, utiliza el constructor `NewBuilder` y configura las credenciales y el endpoint:

```go
builder := bucket.NewMinIO("endpoint", "accessKey", "secretKey").WithSSL()
client, err := builder.GetClient()
if err != nil {
    log.Fatalf("Error creando el cliente: %v", err)
}
```

## Licencia

Este proyecto está licenciado bajo la **Licencia Pública General Affero de GNU, versión 3 (AGPLv3)**.

Esto significa que:
1. Puedes usar, copiar, modificar y distribuir este software libremente.
2. Si realizas modificaciones y utilizas este software como parte de un servicio público (por ejemplo, una API, aplicación web o SaaS), estás obligado a:
   - Liberar el código fuente de las modificaciones realizadas.
   - Asegurarte de que las modificaciones estén disponibles bajo los mismos términos de la AGPLv3.

Puedes encontrar el texto completo de la licencia en el archivo [LICENSE](./LICENSE) o consultarlo en el sitio oficial de GNU:  
[https://www.gnu.org/licenses/agpl-3.0.html](https://www.gnu.org/licenses/agpl-3.0.html).
