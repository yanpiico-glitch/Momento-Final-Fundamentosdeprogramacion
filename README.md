[Ejercicio_momento_final.py](https://github.com/user-attachments/files/30619229/Ejercicio_momento_final.py)
[Uploading Ejercicio_momento_final.py…]()
# Momento-Final-Fundamentosdeprogramacion#Un restaurante gestiona su menú mediante una matriz con 
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
        
