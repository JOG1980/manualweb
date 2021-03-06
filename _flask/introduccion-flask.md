---
title: Introducción a Flask
permalink: /flask/introduccion-flask/
---

Flask es un Microframework de Python que está basado en Werkzeug, Jinja 2 y buenas intenciones. Mediante [Flask][ManualFlask] podemos construir aplicaciones web y servicios Restful con Python de una forma extraordinariamente sencilla. Con pocas líneas podemos llegar a tener un servicio Restful funcionando.

La mayor virtud de [Flask][ManualFlask] es poder crear rutas web de una forma muy sencilla. Una pequeña aplicación web que nos devolviese un hola mundo sería tan sencilla como escribir:

```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "¡Hola Mundo!"

if __name__ == "__main__":
    app.run()
```

O crear un servicio que sumase dos números con [Flask][ManualFlask] lo podríamos hacer con el siguiente código:

```python
from flask import Flask
app = Flask(__name__)

@app.route('/suma/<int:s1>/<int:s2>',methods=['GET'])
def suma(s1,s2):
    return str(s1+s2)

if __name__ == '__main__':
    app.run()
```

En <samp>http://localhost:5000/</samp> se tendrá el resultado del código.

### Características de Flask
* **Micro**, es un framework pequeño, pero extensible. La idea de [Flask][ManualFlask] es que en una sola página pueda caberte una aplicación web. Por ejemplo, por defecto [Flask][ManualFlask] no trae una capa de abstracción de base de datos. Si bien ya existen múltiples extensiones que agregan dicha capacidad.


### Estructura de un proyecto Flask
Por convención los proyectos [Flask][ManualFlask] tienen la siguiente estructura:

* **static**, para los ficheros estáticos.
* **templates**, para las plantillas.

[ManualFlask]: http://www.manualweb.net/tutorial-flask/
