# Proyecto Final Coder House - Python
#### Comisión: 27615
#### Alumno: Johannes Pérez

## Nombre del Proyecto
Venta y Permuta de Instrumentos Musicales

## Versión
1.0

## Descripción del Proyecto
Página Web destinada a usuarios que deseen vender o permutar instrumentos musicales.

A fin de navegar por las secciones de la página web, el usuario será requerido iniciar sesión o registrarse en caso de no contar con usuario o contraseña. En ambas opciones, una vez la página valide la autenticación del usuario, este será redirigido al inicio de la página web.

Los usuarios pueden realizar las siguientes accciones:
- Publicar instrumentos musicales
- Visualizar instrumentos musicales publicados, los cuales están distribuidos en las secciones "Guitarras", "Bajos", "Pedales", "Amplificadores", "Teclados" y "Otros"
- Comentar instrumentos musicales
- Editar el perfil de Usuario
- Cambiar la contraseña de Usuario
- Cerrar Sesión
- Login en caso de haber cerrado sesión

Nota: La opción de editar y eliminar instrumentos musicales solo le está permitido al autor de la publicación del instrumento.

## Tecnología Utilizada

##### Front-End
- HTML 5
- CSS 3
- Javascript ES6
- Bootstrap 5.2

##### Back-End
- Python 3.10.4
- Django 4.0

## Pruebas Realizadas

Ver archivo titulado "Pruebas Proyecto Python CH.xlsx" el cual se encuentra en el presente repositorio https://github.com/johannesgperez/ProyectoFinalMain.git

## Video Demostración

https://youtu.be/O3tgo0Txl9Q









# DJANGO PROJECT

#### Install entorno virtual para elproyecto django
```
$ pip install virtualenv
```
#### Crear el entorno vitual
```
$ virtualenv venv
o
$ python3 -m venv venv
```
#### Activar el entorno
```
$ source venv/bin/activate
```
### Instalar Django
```
$ pip install django

Collecting django
  Using cached Django-5.0-py3-none-any.whl.metadata (4.1 kB)
Collecting asgiref>=3.7.0 (from django)
  Using cached asgiref-3.7.2-py3-none-any.whl.metadata (9.2 kB)
Collecting sqlparse>=0.3.1 (from django)
  Using cached sqlparse-0.4.4-py3-none-any.whl (41 kB)
Collecting typing-extensions>=4 (from asgiref>=3.7.0->django)
  Downloading typing_extensions-4.9.0-py3-none-any.whl.metadata (3.0 kB)
Using cached Django-5.0-py3-none-any.whl (8.1 MB)
Using cached asgiref-3.7.2-py3-none-any.whl (24 kB)
Downloading typing_extensions-4.9.0-py3-none-any.whl (32 kB)
Installing collected packages: typing-extensions, sqlparse, asgiref, django
Successfully installed asgiref-3.7.2 django-5.0 sqlparse-0.4.4 typing-extensions-4.9.0

[notice] A new release of pip is available: 23.3.1 -> 23.3.2
[notice] To update, run: pip install --upgrade pip
```
Solicita actualizar pip

```
$ pip install --upgrade pip

Requirement already satisfied: pip in ./venv/lib/python3.10/site-packages (23.3.1)
Collecting pip
  Using cached pip-23.3.2-py3-none-any.whl.metadata (3.5 kB)
Using cached pip-23.3.2-py3-none-any.whl (2.1 MB)
Installing collected packages: pip
  Attempting uninstall: pip
    Found existing installation: pip 23.3.1
    Uninstalling pip-23.3.1:
      Successfully uninstalled pip-23.3.1
Successfully installed pip-23.3.2
```
#### verificar si esta instalado correctamente
```
$ django-admin --version

o

$ python -m django --version
```
### Creando el proyecto 

```
django-admin startproject PlaygroundFinalProjectArenas
```

### Creando la aplicacion
```
$ cd PlaygroundFinalProjectArenas
$ python manage.py startapp blog_app
```
### Rutas


### Definiendo los models utilizando las clases de Django.
```
from django.db import models
from django.contrib.auth.models import User

class Blog(models.Model):
    title = models.CharField(max_length=100)
    subtitle = models.CharField(max_length=200)
    body = models.TextField()
    author = models.ForeignKey(User, on_delete=models.CASCADE)
    date = models.DateField()
    image = models.ImageField(upload_to='blog_images')

    def __str__(self):
        return self.title
```