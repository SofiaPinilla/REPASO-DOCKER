# REPASO DE DOCKER 4

Crea una carpeta por ejercicio. Utiliza `python:3.11-slim` como imagen base y ejecuta todos los programas y tests dentro de Docker.

## Ejercicio 1. Bucle del 1 al 10

- Crea un `main.py` que muestre los números del 1 al 10 mediante un bucle `for`.
- Crea un `Dockerfile`, construye la imagen y ejecuta un contenedor.
- Lista las imágenes y los contenedores. Elimina el contenedor que has creado.

## Ejercicio 2. Pares e impares

- Crea un `main.py` que recorra los números del 1 al 10 e indique si son pares o impares.
- Dockeriza el programa y ejecútalo.
- Modifica el bucle para que llegue hasta el 15. Ejecuta la imagen sin reconstruirla y después reconstruyéndola. ¿Qué diferencia observas?

## Ejercicio 3. Contador de vocales

- Crea una función `contar_vocales(palabra)` que devuelva el número de vocales (sin tildes, incluyendo mayúsculas).
- Muestra por consola el resultado de `contar_vocales("docker")`. Debe devolver `2`.
- Dockeriza el programa utilizando `/app` como directorio de trabajo.
- Cambia la palabra a `AEIOU` y ejecuta el programa utilizando un bind mount, sin reconstruir la imagen. Debe mostrar `5`.

## Ejercicio 4. Función y Pytest

- Crea en `main.py` una función `es_par(numero)` que devuelva `True` si el número es par y `False` si es impar.
- Crea un `test_main.py` con un test para cada caso:
  - `es_par(4)` → `True`.
  - `es_par(7)` → `False`.
  - `es_par(0)` → `True`.
- Crea un `requirements.txt` con pytest.
- Crea un `Dockerfile` que instale las dependencias y ejecute los tests.
- Construye la imagen y comprueba que pasan los tres tests dentro del contenedor.

## Ejercicio 5. Validador de contraseñas

- Crea una función `validar_password(password)` que devuelva `True` si la contraseña tiene al menos 8 caracteres y contiene algún dígito del 0 al 9. Si no, devuelve `False`.
- Crea un test para cada caso:
  - `docker123` → `True`.
  - `abcdefgh` → `False`.
  - `abc123` → `False`.
- Dockeriza y ejecuta los tests.
- Añade un cuarto test para la contraseña `abcd1234` (resultado esperado: `True`) y vuelve a ejecutar los tests mediante un bind mount, sin reconstruir la imagen.

## Ejercicio 6. Docker Compose

- Copia el `main.py` del ejercicio 3 en una carpeta nueva.
- Crea un `compose.yaml` que utilice la imagen oficial de Python, un bind mount y ejecute el programa. No utilices Dockerfile.
- Ejecuta el programa con Docker Compose.
- Cambia la palabra y vuelve a ejecutarlo.

## Ejercicio 7. Pytest con Docker Compose

Reutiliza el código, los tests y el `requirements.txt` del ejercicio 4 en una carpeta nueva.

**Parte A:** Crea un `compose.yaml` que utilice la imagen oficial de Python y un bind mount. Instala las dependencias al arrancar y ejecuta pytest.

**Parte B:** Crea un `Dockerfile` que instale las dependencias al construir la imagen y ejecute pytest. Modifica el `compose.yaml` para utilizar `build` en lugar de la imagen oficial y elimina el comando de instalación anterior.

Comprueba que pasan los tres tests en ambas partes.
