# LABORATORIO N°3 - CRUD CON LARAVEL

## INTRODUCCIÓN

Este laboratorio tuvo como objetivo implementar un sistema CRUD (Create, Read, Update, Delete) completo en Laravel para la gestión de productos. Se trabajó con el generador de código `ibex/crud-generator` para automatizar la creación de controladores, vistas, modelos y rutas, aplicando los conceptos fundamentales del patrón Modelo-Vista-Controlador (MVC) en el framework Laravel.

El CRUD implementado permite:
- **Crear** nuevos productos con descripción, precio y stock
- **Listar** todos los productos existentes
- **Visualizar** detalles de productos específicos
- **Editar** información de productos
- **Eliminar** productos del sistema

## REQUISITOS PREVIOS

Para ejecutar este proyecto, se requiere el siguiente ecosistema de desarrollo:

- **PHP 8.2.26** o superior
- **Composer** (última versión estable)
- **Laravel 12.5.0**
- **Servidor local:** WampServer
- **Base de datos:** MySQL (phpMyAdmin)
- **Editor:** Visual Studio Code
- **Node.js y npm** (para compilación de assets front-end)
- **Sistema operativo:** Windows 10/11

## DEPENDENCIAS Y COMANDOS PRINCIPALES

```bash
# Creación del proyecto
composer create-project laravel/laravel crud_rapido

# Configuración de entorno
php artisan key:generate

# Configuración de base de datos (modificar .env)
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=crud_rapido
DB_USERNAME=root
DB_PASSWORD=

# Creación de modelo y migración
php artisan make:model Product -m

# Ejecución de migraciones
php artisan migrate:fresh

# Instalación del generador CRUD
composer require ibex/crud-generator --dev
php artisan vendor:publish --tag=crud
php artisan make:crud products

# Instalación de UI y assets
composer require laravel/ui --dev
php artisan ui bootstrap
npm install
npm run dev

# Ejecución del servidor
php artisan serve

```
## FLUJO DE TRABAJO DEL LABORATORIO
- **Configuración** inicial del proyecto Laravel y entorno de desarrollo
- **Configuración** de base de datos en archivo .env
- **Creación** del modelo Product con migración correspondiente
- **Protección** contra asignación masiva usando $fillable
- **Generación** automática de recursos CRUD con ibex/crud-generator
- **Configuración** de rutas para operaciones CRUD
- **Instalación** y compilación de assets front-end
- **Solución** de errores y despliegue final
- 
## BASE DE DATOS
Estructura de la tabla products

```
CREATE TABLE products (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    description VARCHAR(255) NOT NULL,
    price DECIMAL(8,2) NOT NULL,
    stock INTEGER NOT NULL,
    created_at TIMESTAMP,
    updated_at TIMESTAMP
);
```
## Migración aplicada
```
public function up(): void
{
    Schema::create('products', function (Blueprint $table) {
        $table->id();
        $table->string('description');
        $table->decimal('price', 8, 2);
        $table->integer('stock');
        $table->timestamps();
    });
}
```
## RESULTADOS OBTENIDOS
El sistema implementado permite:

✅ Crear productos con validación de datos

✅ Listar productos en interfaz tabular

✅ Editar productos existentes

✅ Eliminar productos con confirmación

✅ Persistencia de datos en base de datos MySQL

✅ Navegación completa entre vistas CRUD

## Evidencia de funcionamiento:
<img width="1036" height="288" alt="image" src="https://github.com/user-attachments/assets/e8e1940c-1372-4164-8e4c-9151d15a23af" />
<img width="1021" height="378" alt="image" src="https://github.com/user-attachments/assets/65f323ba-1ccc-4915-91de-7d90353baec7" />
<img width="1054" height="326" alt="image" src="https://github.com/user-attachments/assets/f3e86cc6-6e23-4831-9acb-800900310dba" />
<img width="776" height="123" alt="image" src="https://github.com/user-attachments/assets/b86ea615-b8ca-4b50-9110-0ad6494da9ca" />

- **Producto** "Clavo" creado exitosamente con precio $0.50 y stock 50
- **Datos** persistentes verificados en phpMyAdmin
- **Operaciones** CRUD completamente funcionales

## REFERENCIAS
- **Documentación** Oficial de Laravel
- **ibex/crud-generator** Documentation
- **Laravel** UI Package
- **Stack** Overflow - Laravel Issues

## INFORMACIÓN DEL DESARROLLADOR
Estudiante: Anie Luo

Correo: anie.luo@utp.ac.pa

Grupo: 1SF131

Curso: Ingeniería Web

Facilitadora: Irina Fong

Universidad: Universidad Tecnológica de Panamá

Facultad: Ingeniería en Sistemas Computacionales

Licenciatura: Ingeniería de Software


## FECHAS
Fecha de ejecución: Octubre 2025

Fecha de entrega: 6 de Octubre 2025

II Semestre 2025

