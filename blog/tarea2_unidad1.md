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

reto1()
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



