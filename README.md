# 📚 BibliotecaDB – Módulo de Login  
Sistema de Gestión de Bibliotecas  
Proyecto Académico de Ingeniería de Software  

---

## 📌 Descripción General  
**BibliotecaDB** es la base de datos diseñada para el módulo de **autenticación (Log-in)** del Sistema de Gestión de Bibliotecas desarrollado por el equipo.  
Este repositorio centraliza todos los recursos relacionados con la creación, documentación y pruebas del modelo de datos.

El enfoque principal es garantizar una arquitectura segura y correctamente normalizada para la gestión de usuarios, roles y datos personales.

---

## 🛠️ Tecnologías Utilizadas  
- **SQL Server 2019+**  
- **T-SQL (Transact-SQL)**  
- **PowerDesigner (modelo físico y lógico)**  
- **UML (casos de uso y clases)**  
- **Modelo relacional normalizado (1FN, 2FN, 3FN)**

---

## 🗂️ Contenido del Repositorio  

| Carpeta / Archivo | Descripción |
|-------------------|-------------|
| `/sql/` | Scripts SQL para crear la base de datos y tablas |
| `/diagramas/` | ERD, UML, modelo lógico y físico |
| `/documentacion/` | Documento técnico completo (PDF) |
| `/datos-prueba/` | Inserts de prueba (Personas, Usuarios, Roles) |
| `README.md` | Archivo principal con la descripción del proyecto |

---

## 🧩 Estructura del Modelo de Datos  

El módulo de Login se basa en tres entidades principales:

### **1. Persona**  
Almacena los datos personales del usuario.
- Nombre  
- Apellido  
- Cédula  
- Teléfono  
- Email  
- Dirección  
- FechaRegistro  

### **2. Rol**  
Define los roles del sistema:
- Administrador  
- Bibliotecario  
- Usuario  

### **3. Usuario**  
Gestiona credenciales y seguridad.
- NombreUsuario  
- Salt  
- ContrasenaHash  
- Estado  
- FechaCreacion  

Relaciones:
- **Persona 1..1 — 1..1 Usuario**  
- **Rol 1..N Usuario**

---

## 🔐 Seguridad Implementada  

El sistema implementa parámetros modernos de seguridad:

- **Hash + Salt** personalizado (VARBINARY en base de datos)  
- Almacenamiento seguro sin contraseñas en texto plano  
- Estructura preparada para autenticación con **JWT**, OAuth o API REST  

---

## 🧪 Datos de prueba incluidos  

El repositorio incluye inserts para:

- 3 roles (Administrador, Bibliotecario, Usuario)  
- 3 personas  
- 3 usuarios con hash y salt simulados para pruebas  

---

## 📥 Instalación y Ejecución  

### **1️⃣ Abrir SQL Server Management Studio (SSMS)**  
Conéctate a tu servidor local.

### **2️⃣ Crear la base de datos**
```sql
CREATE DATABASE BibliotecaDB;
GO
USE BibliotecaDB;
