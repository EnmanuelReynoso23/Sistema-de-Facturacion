# Sistema de Facturación - Base de Datos Relacional

[![Database](https://img.shields.io/badge/Database-MySQL-blue)](https://mysql.com)
[![SQL](https://img.shields.io/badge/Language-SQL-orange)](https://www.w3schools.com/sql/)
[![Normalización](https://img.shields.io/badge/Normalización-3NF-green)](https://es.wikipedia.org/wiki/Tercera_forma_normal)

## Equipo de Desarrollo

| Desarrollador      | Rol                                  |
| ------------------ | ------------------------------------ |
| **Ryan**     | Procedimientos de almacenados        |
| **Noelia**   | Tablas de la base de datos con Anael |
| **Enmanuel** | Esquema y Diccionario                |
| **Anael**    | Tablas de la base de datos           |

## Descripción del Proyecto

Sistema integral de facturación que permite gestionar de manera eficiente toda la información relacionada con clientes, productos, ventas, facturación, pagos y cuentas por cobrar. La base de datos está diseñada siguiendo las mejores prácticas de normalización y garantiza la integridad referencial.

## Objetivos

- Diseñar una base de datos relacional normalizada
- Implementar integridad referencial
- Crear procedimientos almacenados eficientes
- Garantizar la consistencia de los datos
- Facilitar consultas complejas entre múltiples tablas

## Diseño del Modelo Relacional

### Entidades Principales

#### **CLIENTES**

#### **PRODUCTOS**

- **ID_Producto** (PK) - INT AUTO_INCREMENT

#### **USUARIOS**

#### **FACTURAS**

#### **DETALLE_FACTURA**

#### **PAGOS**

#### **CUENTAS_POR_COBRAR**

### Relaciones entre Entidades

```sql


## Tecnologías Utilizadas

- **SGBD**: MySQL 8.0+
- **Lenguaje**: SQL
- **Herramientas**: MySQL Workbench, phpMyAdmin
- **Normalización**: Tercera Forma Normal (3NF)

## Estructura del Proyecto

```

sistema-facturacion/
├── database/
│   ├── 01_create_database.sql
│   ├── 02_create_tables.sql
│   ├── 03_foreign_keys.sql
│   ├── 04_indexes.sql
│   └── 05_sample_data.sql
├── stored_procedures/
│   ├── clientes/
│   │   ├── sp_insertar_cliente.sql
│   │   ├── sp_actualizar_cliente.sql
│   │   └── sp_consultar_clientes.sql
│   ├── productos/
│   │   ├── sp_insertar_producto.sql
│   │   ├── sp_actualizar_producto.sql
│   │   └── sp_consultar_productos.sql
│   └── facturas/
│       ├── sp_crear_factura.sql
│       ├── sp_consultar_facturas.sql
│       └── sp_reporte_ventas.sql
├── queries/
│   ├── consultas_basicas.sql
│   ├── consultas_complejas.sql
│   └── reportes.sql
├── docs/
│   ├── diagrama_er.png
│   ├── diccionario_datos.md
│   └── manual_usuario.md
└── README.md

```

## Instalación y Configuración

El proyecto requiere la instalación de un Sistema de Gestión de Base de Datos MySQL y la ejecución secuencial de los scripts de creación de base de datos, tablas, relaciones e índices. Los procedimientos almacenados deben ser implementados siguiendo la estructura modular propuesta.

## Exportar e Importar la Base de Datos Completa (PostgreSQL)

### Exportar (crear backup.sql)

1. Abre PowerShell en la carpeta del proyecto.
2. Ejecuta:
   ```powershell
   pg_dump -U postgres -p 2525 -d sistema_facturacion > backup.sql
   ```
3. Sube el archivo `backup.sql` al repositorio de GitHub.

### Importar (restaurar backup.sql)

1. Clona el repositorio y ve a la carpeta del proyecto.
2. Abre PowerShell y ejecuta:
   ```powershell
   psql -U postgres -p 2525 -d sistema_facturacion -f backup.sql
   ```
3. La base de datos se restaurará con toda la estructura y datos.

---

## Criterios de Normalización Aplicados

### Primera Forma Normal (1NF)
- Todos los atributos contienen valores atómicos
- No hay grupos repetitivos
- Cada fila es única

### Segunda Forma Normal (2NF)
- Cumple 1NF
- Todos los atributos no clave dependen completamente de la clave primaria
- Eliminación de dependencias parciales

### Tercera Forma Normal (3NF)
- Cumple 2NF
- No existen dependencias transitivas
- Cada atributo no clave depende directamente de la clave primaria

## Integridad Referencial

### Restricciones Implementadas
- **CASCADE**: Eliminación en cascada para registros dependientes
- **RESTRICT**: Prevención de eliminación si existen referencias
- **SET NULL**: Establecer valor nulo en caso de eliminación del padre

Las restricciones de integridad referencial garantizan la consistencia de los datos y previenen operaciones que puedan comprometer la integridad del sistema.

## Testing y Verificación

El sistema incluye scripts de verificación para garantizar:
- Integridad referencial entre todas las tablas
- Consistencia de datos en stocks y transacciones
- Validación de reglas de negocio implementadas
- Pruebas de rendimiento de consultas complejas

## Métricas de Rendimiento

- **Índices Optimizados**: Creados en campos de búsqueda frecuente
- **Consultas Eficientes**: Tiempo promedio < 100ms
- **Normalización 3NF**: Minimización de redundancia de datos
- **Integridad**: 100% de consistencia referencial

## Instalación Automática con setup_db.ps1

1. Abre PowerShell como administrador.
2. Ve a la carpeta del proyecto (ejemplo si está en Descargas):
   ```powershell
   cd "C:\Users\reyno\Downloads\Sistemas-de-base-de-datos-Trabajo-final-40p"
   ```
3. Ejecuta el script:
   ```powershell
   .\setup_db.ps1
   ```
4. Ingresa la contraseña de PostgreSQL cuando lo pida.

Esto creará la base de datos, los esquemas y ejecutará todos los scripts de estructura automáticamente.
