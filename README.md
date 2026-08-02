
# Sistema de Gestión de Menú y Descuentos - Restaurante

Este repositorio contiene la solución automatizada en Python para la gestión de precios y promociones del menú de un restaurante mediante el uso de estructuras matriciales.

## Requisitos Implementados
* **Estructura Matricial:** Matriz con 6 productos distribuidos en categorías de `Comida` y `Bebida`.
* **Modularidad:** Función `calcular_precio_final` encargada de procesar de manera independiente la lógica de negocio de cada artículo.
* **Lógica de Promoción (15%):** El descuento se aplica de manera estricta únicamente si el producto pertenece a la categoría objetivo (`Comida`) y su precio base es estrictamente superior al umbral dinámico ingresado por el usuario.

## Ejecución del Proyecto
Para ejecutar el script del menú, abre tu terminal y escribe:
```bash
python menu_restaurante.py
```
[Ejercicio_momento_final.py](https://github.com/user-attachments/files/30619353/Ejercicio_momento_final.py)
#Un restaurante gestiona su menú mediante una matriz con 
#el siguiente formato: 
#[Nombre del producto, Categoría, Precio base] 
#Se requiere implementar una funcionalidad que aplique una promoción a 
#ciertos productos del menú.



def calcular_precio_final(producto, categoria_objetivo, precio_umbral):
    #  Sacamos la categoría y el precio del producto usando sus posiciones
    categoria_producto = producto[1].lower()
    precio_base = producto[2]

    #  Si coincide la categoría Y además supera el precio mínimo, aplicamos descuento
    if categoria_producto == categoria_objetivo.lower() and precio_base > precio_umbral:
        descuento = precio_base * 0.15
        return precio_base - descuento
    
    
    return precio_base


def main():
    print("=== Sistema de Gestión de Promociones ===")

   
    menu_restaurante = [
        ["Hamburguesa Especial", "Comida", 25000.0],
        ["Papas Fritas", "Acompañamiento", 8000.0],
        ["Pizza Familiar", "Comida", 45000.0],
        ["Jugo Natural", "Bebida", 6500.0],
        ["Gaseosa 1.5L", "Bebida", 9000.0],
        ["Tres Leches", "Postre", 12000.0]
    ]

    
    categoria_objetivo = input("Ingrese la categoría para la promoción: ")
    precio_umbral = float(input("Ingrese el umbral de precio mínimo ($): "))

    print("\n=== REPORTE DEL MENÚ ===")

   
    for producto in menu_restaurante:
        nombre = producto[0]
        precio_base = producto[2]
        
       
        precio_final = calcular_precio_final(producto, categoria_objetivo, precio_umbral)
        
       
        print(f"Producto: {nombre}")
        print(f"  -> Precio Base:  ${precio_base}")
        print(f"  -> Precio Final: ${precio_final}")
        
        if precio_final < precio_base:
            print("  [¡Promoción Aplicada del 15%!]")
        print("-" * 30)



main()

