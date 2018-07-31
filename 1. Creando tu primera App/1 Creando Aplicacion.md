# CREANDO UNA NUEVA APLICACION
## CREAR APLICACION
Una vez el bench esté instalado, vas a ver dos directorios principales, **apps** y **sites**. Todas las aplicaciones van a ser instaladas en apps.

Para crear una nueva aplicación, debes posicionarte en el directorio del bench y ejecutar `bench new-app {app_name}` y llenar los detalles de la aplicación. Esto a va crear los directorios y archivos necesarios para una aplicación.

Ejemplo:
```
$ bench new-app library_management
```

Datos a especificar:
```
App Title (defaut: Lib Mgt): Library Management
App Description:  App for managing Articles, Members, Memberships and Transactions for Libraries
App Publisher: Frappe
App Email: info@frappe.io
App Icon (default 'octicon octicon-file-directory'): octicon octicon-book
App Color (default 'grey'): #589494
App License (default 'MIT'): GNU General Public License
```
## ESTRUCTURA DE UNA APLICACIÓN
La aplicación va a ser creada en el directorio llamado library_management y va a tener la siguiente estructura:
```
.
├── MANIFEST.in
├── README.md
├── library_management
│   ├── __init__.py
│   ├── config
│   │   ├── __init__.py
│   │   └── desktop.py
│   ├── hooks.py
│   ├── library_management
│   │   └── __init__.py
│   ├── modules.txt
│   ├── patches.txt
│   └── templates
│       ├── __init__.py
│       ├── generators
│       │   └── __init__.py
│       ├── pages
│       │   └── __init__.py
│       └── statics
├── license.txt
├── requirements.txt
└── setup.py
```
1. **config** contiene la información de configuración de la aplicación.
2. **desktop.py** es donde los íconos del escritorio pueden ser agregados al mismo.
3. **hooks.py** es donde se configuran las integraciones con el entorno y otras aplicaciones.
4. **library_management** (dentro) es un módulo que está contenido. En Frappe, un módulo es donde los modelos y controladores se almacenan.
5. **modules.txt** contiene la lista de módulos en la aplicación. Cuando creas un nuevo módulo, es obligatorio que lo agregues a este archivo.
6. **patches.txt** es donde los patches para migraciones son establecidos. Son módulos de Python referenciados usando la nomenclatura de punto.
7. **templates** es el directorio donde son mantenidos las plantillas de vistas web. Plantillas para Login y otras páginas estandar estan contenidas en Frappe.
8. **generators** son donde las plantillas para los modelos son almacenadas, donde cada instancia de modelo tiene una ruta web separada, por ejemplo un Blog Post donde cada post tiene una url única. En Frappe, el manejador de plantillas utilizado es Jinja2.
9. **pages** es donde las rutas simples son almacenadas. Por ejemplo para un tipo de página "/blog".