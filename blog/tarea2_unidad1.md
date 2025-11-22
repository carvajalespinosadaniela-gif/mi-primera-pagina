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

```python
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

```
### Explicación
En este reto le pido al usuario dos números con input(): uno para saber cuántos pasos debe moverse la tortuga hacia la derecha y otro para saber cuántos pasos debe bajar Primero dibujo la parte horizontal de la “L” colocando la tortuga 🐢 seguida de tantos guiones
 - como dijo el usuario. Luego preparo un grupo de espacios para que la parte vertical quede alineada al final de esa línea horizontal.
Con un ciclo for, imprimo el símbolo | hacia abajo tantas veces como pasos ingresó el usuario.
 Al final, el programa muestra un mensaje confirmando que la tortuga dibujó una “L” con los pasos indicados.

### Ejemplo de salida del programa

```python
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
```
## Reto 4 - Encapsular los movimientos en funciones
### Explicación
  
En este reto debemos convertir los movimientos de la tortuga en funciones. La idea es crear adelante(n) para avanzar hacia la derecha y abajo(n) para bajar, usando solo texto. Luego debemos usarlas para dibujar una figura sencilla, como una “L”.

### Ejemplo de salida del programa

```python
# Variable global para llevar el control de la posición horizontal
posicion_x = 0

def adelante(n):
    """
    Mueve la tortuga hacia la derecha.
    """
    global posicion_x
    # Imprimir la tortuga y su rastro de flechas
    linea = " " * posicion_x + "🐢" + "→" * (n - 1)
    print(linea)
    posicion_x += n  # actualizar posición

def abajo(n):
    """
    Mueve la tortuga hacia abajo.
    """
    global posicion_x
    for _ in range(n):
        print(" " * (posicion_x - 1) + "↓")

def reto4():
    print("=== Reto 4: funciones adelante() y abajo() ===")
    # Dibujar una L solo usando nuestras funciones
    adelante(5)
    abajo(3)

# Ejecutar solo el reto 4
reto4()
```

### Explicación  
En este reto tuve que convertir el movimiento de la tortuga en funciones para que el código fuera más fácil de usar. Hice una función adelante(n) que imprime las flechas hacia la derecha y otra llamada abajo(n) que baja la tortuga usando flechas hacia abajo. Para que ambas funcionen bien, guardo la posición horizontal en una variable y así todo queda alineado. Al final solo llamo esas funciones y la tortuga termina dibujando una “L” usando puro texto.

### Ejemplo de salida del programa

```python
=== Reto 4: funciones adelante() y abajo() ===
🐢→→→→
    ↓
    ↓
    ↓
```
    ## Reto 5
###Enunciado
Ajusta tus funciones para que la tortuga pueda bajar escalones.
Cada escalón debe conservar la posición horizontal acumulada y dibujar correctamente tanto el tramo horizontal como el vertical.
### Mi solución
```python
# =========================================================
# 1. ESTADO GLOBAL (Necesario para recordar la posición)
# =========================================================
posicion_x = 0  # Posición horizontal (indentación)

# =========================================================
# 2. FUNCIONES DE MOVIMIENTO CON ESTADO
# =========================================================

def adelante(n):
    """
    Dibuja el movimiento hacia la derecha (+) y actualiza la posición horizontal.
    """
    global posicion_x
    if n > 0:
        # 1. Imprime los espacios de indentación acumulados hasta ahora
        indentacion = " " * posicion_x
        
        # 2. Dibuja el tramo horizontal (usamos '+' como en tu ejemplo)
        print(indentacion + "+" * n)
        
        # 3. Actualiza la posición X para el siguiente movimiento
        posicion_x += n

def abajo(n):
    """
    Dibuja el movimiento hacia abajo (↓) alineado con la posición horizontal actual.
    """
    global posicion_x
    if n > 0:
        # La indentación se basa en la posición horizontal acumulada
        espacio = " " * posicion_x
        
        # Dibuja cada tramo vertical
        for _ in range(n):
            print(espacio + "↓")
        
        # NOTA: El movimiento vertical NO cambia la posicion_x

# =========================================================
# 3. FUNCIÓN DE COMPOSICIÓN (Dibuja la escalera)
# =========================================================

def escalera(num_escalones, pasos_h, pasos_v):
    """
    Dibuja una serie de escalones, reiniciando la posición_x para empezar.
    """
    global posicion_x
    # Reinicia el estado para que la escalera empiece siempre desde el borde
    posicion_x = 0 
    
    print(f"\n--- Dibujando Escalera de {num_escalones} escalones ---")
    
    for i in range(num_escalones):
        print(f"\n# Escalón {i + 1}")
        adelante(pasos_h)
        abajo(pasos_v)

# =========================================================
# 4. EJECUCIÓN DEL RETO 5
# =========================================================

# Dibuja la escalera del ejemplo: 3 escalones de 5 pasos horizontales y 2 verticales.
escalera(num_escalones=3, pasos_h=5, pasos_v=2)
```
### Explicación 
En este reto la idea fue hacer que la tortuga bajara una escalera hecha completamente con texto. Para eso volví a usar las funciones adelante() y abajo(), pero ahora las combiné una detrás de la otra para formar cada escalón. La tortuga avanza hacia la derecha como si pisara un escalón y luego baja un poco para pasar al siguiente. Todo queda alineado porque voy guardando la posición donde termina cada movimiento. Al final, la tortuga va bajando peldaño por peldaño y la escalera aparece sola en la pantalla solo con impresiones de texto.
### Ejemplo de salida del programa
```python
--- Dibujando Escalera de 3 escalones ---
# Escalón 1
+++++
     ↓
     ↓
# Escalón 2
     +++++
          ↓
          ↓
# Escalón 3
          +++++
               ↓
               ↓
```


