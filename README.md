# Monorepo: Frontend y Backend

Este es un monorepo que contiene los proyectos de frontend y backend como submódulos de Git. El frontend es una aplicación en Angular y el backend está construido con Django y Django Rest Framework (DRF). Ambos proyectos están gestionados de forma independiente en sus propios repositorios, pero están unidos aquí a través de submódulos para facilitar el manejo y el despliegue.

Estructura del Proyecto:
```bash
banking/\
├── frontend/        # Submódulo que contiene el proyecto frontend en Angular\
├── backend/         # Submódulo que contiene el proyecto backend en Django\
├── .gitmodules      # Archivo de configuración para los submódulos de Git\
└── README.md        # Este archivo
```

## Frontend: Angular
El directorio frontend/ contiene una aplicación web hecha en Angular, que interactúa con la API del backend para realizar solicitudes y mostrar datos. El frontend está construido con componentes modernos de Angular, utiliza RxJS para manejar las solicitudes HTTP y está diseñado para consumir la API REST del backend.

Para trabajar con el frontend de forma local, debes navegar al directorio frontend y ejecutar los siguientes comandos:
```bash
cd frontend
npm install  # Instalar las dependencias
ng serve     # Correr la aplicación en modo desarrollo
```
La aplicación se ejecutará en http://localhost:4200 de forma predeterminada.


## Backend: Django
El directorio backend/ contiene una API RESTful hecha con Django y Django Rest Framework. El backend maneja la lógica del negocio, incluida la autenticación, la generación de tokens de seguridad, y las operaciones de transferencia bancaria.

Para ejecutar el backend localmente, sigue estos pasos:
```bash 
cd backend
python3 -m venv venv       # Crear un entorno virtual
venv/bin/activate   # Activar el entorno virtual
pip install -r requirements.txt  # Instalar las dependencias
python manage.py migrate   # Aplicar las migraciones de base de datos
python manage.py runserver # Correr el servidor de desarrollo
```
El backend estará disponible en http://localhost:8000 de forma predeterminada.


## Cómo Trabajar con el Monorepo
Este monorepo utiliza submódulos de Git para incluir los proyectos de frontend y backend, permitiendo que estos proyectos mantengan sus propios repositorios remotos mientras están vinculados a este repositorio principal.


### Clonar el Monorepo y Submódulos
Para clonar el monorepo con los submódulos, debes ejecutar los siguientes comandos:
```bash
git clone https://github.com/eapb99/banking.git
cd monorepo
git submodule update --init --recursive  # Inicializar y actualizar los submódulos
```
Esto descargará tanto el repositorio del monorepo como los submódulos de frontend y backend.


## Actualizar los Submódulos
Si necesitas actualizar los submódulos para obtener los últimos cambios desde sus respectivos repositorios remotos, ejecuta:
```bash
git submodule update --remote
```
Este comando actualizará los submódulos para que apunten a las últimas versiones en sus ramas remotas.

