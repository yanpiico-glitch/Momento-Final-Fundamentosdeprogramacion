# Sistema de Gestión de Menú y Descuentos - Restaurante

Este repositorio contiene la solución en Python al Problema 2, enfocado en administrar el menú de un restaurante mediante matrices y automatizar la aplicación de promociones selectivas.

## Lógica de la Promoción
Se aplica un **15% de descuento** únicamente si el producto cumple ambas condiciones:
1. Pertenece a la categoría objetivo: `Platos Fuertes`.
2. Su precio base es estrictamente mayor a: `$40,000`.

## Instrucciones de Uso
Ejecuta el archivo principal usando la terminal:
```bash
python menu_restaurante.py
```

---

### 3. Guion de Sustentación para tu video de YouTube (Problema 2)
Usa esta guía de 3 pasos durante tu grabación de pantalla:

*   **Paso 1 - Introducción (0:00 - 0:30):** *"Buen día, mi nombre es [Tu Nombre]. En esta ocasión presentaré el desarrollo del Problema 2, el cual modela el menú de un restaurante mediante una estructura matricial y evalúa promociones automatizadas bajo condiciones específicas."*
*   **Paso 2 - Explicación del Código (0:30 - 1:45):** Muestra el código. *"He creado la lista `matriz_menu` que almacena 6 productos estructurados con su nombre, categoría y precio. Para cumplir con la modularidad requerida, implementé la función `calcular_precio_final`. Esta evalúa mediante un condicional `if` si el producto pertenece a la categoría objetivo ('Platos Fuertes') y supera el umbral de precio ($40,000) para aplicar el 15% de descuento; de lo contrario, mantiene su valor original."*
*   **Paso 3 - Demostración y Cierre (1:45 - 2:30):** Ejecuta el script. *"Al correr el programa, vemos en la consola que la 'Hamburguesa Especial' y las 'Costillas BBQ' se reducen de precio correctamente por cumplir con los requisitos. El código fuente público queda a su disposición en el enlace de GitHub que encontrarán en la descripción de este video."*

<FollowUp>
Ahora que elegiste el Problema 2, ¿prefieres que usemos **valores en dólares** o alguna **moneda local específica** para los precios en el ejercicio?
</FollowUp>
[Ejercicio_momento_final.py](https://github.com/user-attachments/files/30619276/Ejercicio_momento_final.py)

[Ejercicio_momento_final.py](https://github.com/user-attachments/files/30619280/Ejercicio_momento_final.py)

#Un restaurante gestiona su menú mediante una matriz con 
#el siguiente formato: 
#[Nombre del producto, Categoría, Precio base] 
#Se requiere implementar una funcionalidad que aplique una promoción a 
#ciertos productos del menú.



print("Bienvenido al sistema de gestión del menú del restaurante.   ")

def calcular_precio_final( producto,categoria, precio_umbral):
   
try:
menu = [["Hamburguesa","Comida", 5000.0],
["Pizza","Comida", 8000.0], 
["Ensalada","Comida", 4000.0],
["Coca-Cola","Bebida", 2000.0], 
["Agua","Bebida", 1000.0], 
["Cerveza","Bebida", 3000.0]]



Opcion_elegida= input("Ingrese la opcion que desea seleccionar: ").strip()

while True:
    try:
        precio_umbral = float(input("Ingrese el precio umbral para aplicar la promoción $: "))
        if precio_umbral > 0:
            break
        print("Por favor, ingrese un número positivo.")
    except ValueError:
        print("Entrada inválida. Por favor, ingrese un número válido.")

for producto in menu:  
    
    if producto[2] > precio_umbral:
        producto[2] *= 0.15  # Aplicar un descuento del 15%
        print(f"Se ha aplicado un descuento del 15% a {producto[0]}. Nuevo precio: ${producto[2]:.2f}")
        
