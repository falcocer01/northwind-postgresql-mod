
# 📦 Northwind PostgreSQL - Versión Modificada

Este proyecto es una versión adaptada y extendida de la base de datos clásica Northwind, pensada para prácticas educativas y desarrollo en PostgreSQL. Incluye nuevas funciones orientadas a la gestión moderna de inventario, análisis de ventas y control inteligente de stock.

---

## 📘 Descripción del Proyecto

Northwind representa las operaciones comerciales de una empresa de distribución de alimentos. Esta versión ha sido modificada para:

- Modernizar la estructura usando PostgreSQL
- Incluir campos JSONB, arreglos y tipos avanzados
- Añadir funcionalidades personalizadas como carrito de compras, stock bajo y vistas analíticas

---

## ✨ Nuevas Funcionalidades

- Campo caracteristicas_json (JSONB) y etiquetas (array) en la tabla Products
- Carrito de compras (tabla shopping_cart)
- Función vaciar_carrito(p_customer_id)
- Vistas de análisis: ventas diarias, por país, por categoría, por empleado y más
- Vistas de ranking de clientes y productos

---

## 🛠 Tecnologías Utilizadas

- PostgreSQL 15 o superior
- pgAdmin 4 (opcional)
- SQL (PL/pgSQL)
- pg_dump / pg_restore

---

## 📁 Estructura del Repositorio

.
├── backup_northwindo.sql          # Dump completo de la base de datos modificada  
├── README.md                      # Este documento  
└── scripts/                       # (opcional) Scripts organizados por funcionalidad

---

## ⚙️ Instalación Rápida

### 🔑 Prerrequisitos

- PostgreSQL instalado
- pgAdmin 4 o cliente psql
- Usuario con permisos de creación de base de datos

### 🚀 Instalación en 3 pasos

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/tu_usuario/northwind-postgresql-mod.git
   cd northwind-postgresql-mod
   ```

2. Crear la base de datos:

   ```bash
   createdb northwind_mod
   ```

3. Restaurar el dump completo:

   ```bash
   psql -U tu_usuario -d northwind_mod -f backup_northwindo.sql
   ```

---

## 💻 Alternativa con pgAdmin

1. Crear nueva base de datos: northwind_mod
2. Ir a "Restore" > Seleccionar el archivo backup_northwindo.sql
3. Asegurarse de marcar "Format: Plain" y presionar "Restore"

---

## ⚙️ Funcionalidades Principales

### 🛒 Modificación de la tabla Products

- Nuevos campos:
  - caracteristicas_json (JSONB)
  - etiquetas (text[])

### 📦 Control de Stock Inteligente

- Vista productos_stock_bajo: muestra productos con unidades en stock menores a 10

### 🧠 Propuesta del Alumno

- Tabla shopping_cart para simular compras
- Vista carrito_cliente_total
- Función vaciar_carrito(p_customer_id)

---

## 🆕 Nuevas Tablas Añadidas

- shopping_cart
- shopping_cart_cart_id_seq (secuencia)

---

## 👁️‍🗨️ Vistas Creadas

- carrito_cliente_total
- productos_stock_bajo
- vw_top_clientes
- vw_top_productos
- vw_ventas_categoria
- vw_ventas_diarias
- vw_ventas_empleado
- vw_ventas_mes
- vw_ventas_pais

---

## 🧠 Funciones y Triggers

- vaciar_carrito(p_customer_id character varying)

(No se detectaron triggers en el dump, pero podrían añadirse posteriormente.)

---

## 🧪 Datos de Prueba

El dump incluye datos de prueba completos para:
- Clientes
- Productos
- Pedidos
- Carrito de compras
- Categorías y más

---

## ✅ Validar Instalación

Ejecutar en psql:

```sql
SELECT * FROM carrito_cliente_total LIMIT 5;
SELECT * FROM productos_stock_bajo;
SELECT vaciar_carrito('ALFKI');
```

---

## 📐 Especificaciones Técnicas

- PostgreSQL versión: 15+
- Codificación: UTF-8
- Esquema principal: public

---

## 🎓 Información Académica

Proyecto práctico basado en la base de datos Northwind adaptado a PostgreSQL para fines educativos. Útil en módulos como:

- Administración de Bases de Datos
- SQL Avanzado
- Consultas y Visualización
- Automatización y Procedimientos

---

## 🧭 Objetivos de Aprendizaje Demostrados

- Adaptar una base de datos legacy a tecnologías modernas
- Implementar campos semiestructurados (JSONB, arreglos)
- Diseñar funciones y vistas personalizadas
- Automatizar lógica de negocio en el motor de base de datos
- Documentar y distribuir proyectos usando Git y GitHub

---

## 📬 Soporte

Para soporte académico, contactar con el docente o tutor asignado. Para dudas técnicas, abrir una Issue en GitHub o contactar por correo.

—
Proyecto desarrollado como propuesta académica de ampliación funcional de Northwind en PostgreSQL.
