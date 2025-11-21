# Tarea 2 - Ejercicios Unidad 1
## Reto1 – Simula el comportamiento de la tortuga usando solo print() e input()
### Enunciado
Intenta recrear el movimiento de la tortuga únicamente con texto, usando funciones, print() e input() para pedir valores al usuario.
### Mi solución en Python
def reto1():
    print("=== Reto 1: Simulación de tortuga ===")

    pasos = int(input("¿Cuántos pasos quieres que avance la tortuga? "))

    print("\nPosición inicial:")
    print("🐢")

    print("\nMovimiento hacia la derecha:")
    linea = "🐢" + "-" * pasos
    print(linea)

    print(f"\nLa tortuga avanzó {pasos} pasos.")

### Explicación
Este programa le pide al usuario un número usando input(), y ese número representa cuántos pasos debe avanzar la tortuga hacia la derecha.
Cuando ingreso el número (por ejemplo, 9), el programa usa ese valor convertido a entero para dibujar una tortuga 🐢 seguida de una línea hecha con guiones.
Como ingresé 9, se muestran 9 guiones, simulando el recorrido que avanzó la tortuga.
### Ejemplo de salida del programa

```
Posición inicial:
🐢

Movimiento hacia la derecha:
🐢---------
La tortuga avanzó 9 pasos.
```
## Reto 2 – Tortuga bajando

### Enunciado
Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente print() e input().
La salida esperada es similar a:

tortuga bajando
### Código del Reto 2

```python
def reto2():
    print("=== Reto 2: tortuga hacia abajo ===")
    pasos = int(input("¿Cuántos pasos quieres que baje la tortuga? "))

    print("\nPosición inicial:")
    print("🐢")

    print("\nMovimiento hacia abajo:")
    for i in range(pasos):
        print("|")

    print(f"\nLa tortuga bajó {pasos} pasos.")
```
### Explicación
En este programa le pido al usuario un número usando input(). Ese número representa cuántos pasos baja la tortuga.
Por ejemplo, si el usuario escribe 15, la tortuga bajará 15 pasos.

Con un ciclo for dibujo una línea vertical (|) por cada paso, y así se ve el movimiento hacia abajo con la cantidad que el usuario ingrese.
Al final, el programa muestra cuántos pasos bajó la tortuga.
### Ejemplo de salida del programa
```python
=== Reto 2: tortuga hacia abajo ===
¿Cuántos pasos quieres que baje la tortuga? 15

Posición inicial:
🐢

Movimiento hacia abajo:
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│

La tortuga bajó 15 pasos.
```
## Reto 3 – Girar y dibujar una “L” con la tortuga

### Enunciado  
En este reto la tortuga primero avanza hacia la derecha y luego baja, como si dibujara una “L”.  
Debo pedirle al usuario cuántos pasos quiere a la derecha y cuántos pasos quiere hacia abajo, usando solamente `print()` e `input()` para dibujar el recorrido.

### Mi solución en Python

def reto3():
    print("=== Reto 3: girar y dibujar una L ===")

    pasos_derecha = int(input("¿Cuántos pasos avanza la tortuga a la derecha? "))
    pasos_abajo = int(input("¿Cuántos pasos baja la tortuga después de girar? "))

    # Primera parte: movimiento hacia la derecha
    print("\nMovimiento hacia la derecha:")
    linea = "🐢" + "-" * pasos_derecha
    print(linea)

    # Segunda parte: movimiento hacia abajo
    print("\nMovimiento hacia abajo:")
    # Espacios para que el palo vertical quede alineado
    espacio = " " * (1 + pasos_derecha)
    for i in range(pasos_abajo):
        print(espacio + "|")

    print("\nLa tortuga dibujó una L con los pasos indicados.")

### Explicación
En este reto le pido al usuario dos números con input(): uno para saber cuántos pasos debe moverse la tortuga hacia la derecha y otro para saber cuántos pasos debe bajar Primero dibujo la parte horizontal de la “L” colocando la tortuga 🐢 seguida de tantos guiones - como dijo el usuario. Luego preparo un grupo de espacios para que la parte vertical quede alineada al final de esa línea horizontal. Con un ciclo for, imprimo el símbolo | hacia abajo tantas veces como pasos ingresó el usuario. Al final, el programa muestra un mensaje confirmando que la tortuga dibujó una “L” con los pasos indicados.

### Ejemplo de salida del programa
```python
La tortuga bajó 30 pasos.
=== Reto 3: girar y dibujar una L ===
¿Cuántos pasos avanza la tortuga a la derecha? 14
¿Cuántos pasos baja la tortuga después de girar? 10

Movimiento hacia la derecha:
🐢--------------

Movimiento hacia abajo:
               |
               |
               |
               |
               |
               |
               |
               |
               |
               |

La tortuga dibujó una L con los pasos indicados.

