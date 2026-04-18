# Tasks List

Aplicación web Django simple para gestionar y mostrar una lista de tareas.

## Descripción

Este proyecto es una pequeña aplicación de ejemplo creada con Django 6.0.3 que muestra una lista de tareas. Incluye:

- Un modelo `Task` con campos de título, descripción y marcas de tiempo.
- Una vista basada en clases (`TaskListView`) para mostrar las tareas existentes.
- Plantillas Django para generar la interfaz HTML.
- Archivos estáticos para estilos CSS simples.
- Configuración de base de datos SQLite por defecto.

## Estructura del proyecto

- `manage.py` - Entrada principal de Django para ejecutar comandos.
- `requirements.txt` - Dependencias del proyecto.
- `db.sqlite3` - Base de datos SQLite local.
- `base_project/` - Proyecto Django principal.
  - `settings.py` - Configuración de Django.
  - `urls.py` - Rutas globales del proyecto.
  - `wsgi.py` / `asgi.py` - Entradas para despliegue.
- `tasks/` - Aplicación Django encargada de las tareas.
  - `models.py` - Definición del modelo `Task`.
  - `views.py` - Vista `TaskListView` para listar tareas.
  - `urls.py` - Ruta raíz que carga la vista principal.
  - `admin.py` - Configuración del panel de administración (por defecto vacío).
  - `tests.py` - Plantilla para pruebas.
- `templates/` - Plantillas HTML.
  - `tasks/_base.html` - Plantilla base.
  - `tasks/tasks_list.html` - Vista de lista de tareas.
- `static/` - Archivos estáticos.
  - `css/base.css` - Estilos básicos.

## Dependencias

El proyecto utiliza las siguientes dependencias declaradas en `requirements.txt`:

- Django==6.0.3
- asgiref==3.11.1
- black==26.3.1
- click==8.3.1
- colorama==0.4.6
- my_py_extensions==1.1.0

> Nota: `black`, `click` y `colorama` son herramientas auxiliares de desarrollo. `my_py_extensions` puede ser una dependencia adicional usada en el entorno de desarrollo.

## Configuración y ejecución

### Requisitos previos

- Python 3.11 (o compatible con Django 6.0.3)
- Virtualenv recomendado

### Instalación

1. Clonar o copiar el proyecto en una carpeta local.
2. Crear y activar un entorno virtual:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3. Instalar dependencias:

```powershell
pip install -r requirements.txt
```

4. Aplicar migraciones:

```powershell
python manage.py migrate
```

### Ejecutar la aplicación

```powershell
python manage.py runserver
```

Luego abrir en el navegador:

```
http://127.0.0.1:8000/
```

### Panel de administración

La aplicación incluye el panel de administración Django en:

```
http://127.0.0.1:8000/admin/
```

Para crear un superusuario compatible con el admin:

```powershell
python manage.py createsuperuser
```

## Modelo principal

La aplicación define un modelo `Task` con los siguientes campos:

- `title` - Nombre o título de la tarea.
- `description` - Descripción de la tarea (opcional).
- `created_at` - Fecha y hora de creación.
- `updated_at` - Fecha y hora de última actualización.

## Rutas principales

- `/` - Página principal que muestra la lista de tareas.
- `/admin/` - Panel de administración Django.

## Personalización

- Agregar tareas desde el admin de Django o extendiendo la aplicación con formularios.
- Añadir nuevos estilos CSS en `static/css/base.css`.
- Extender las plantillas en `templates/tasks/`.

## Notas de desarrollo

- `DEBUG` está activado en `base_project/settings.py`, lo cual es adecuado solo para desarrollo local.
- `SECRET_KEY` está en el repositorio con fines de desarrollo; no debe usarse en producción.
- La base de datos predeterminada es SQLite (`db.sqlite3`).

## Mejoras sugeridas

- Añadir creación/edición/eliminación de tareas.
- Registrar el modelo `Task` en `tasks/admin.py`.
- Agregar pruebas unitarias en `tasks/tests.py`.
- Configurar variables de entorno para `SECRET_KEY` y `DEBUG`.
- Implementar paginación o filtros en la vista de lista.
