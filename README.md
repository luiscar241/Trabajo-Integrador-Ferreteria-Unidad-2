# Trabajo-Integrador-Ferreteria-Unidad-2
"""En una ferretería se quiere implementar un sistema que permita a los usuarios saber cuánto deberán pagar por la compra de lámparas de bajo consumo. 
Se tiene en cuenta que todas las lámparas cuestan $800.
A partir de la cantidad y marca de las lámparas compradas (solo se puede comprar una marca por vez) se aplicará el siguiente descuento:
- Si compra 6 o más  lámparas bajo consumo tiene un descuento del 50%. 
- Si compra 5  lámparas bajo consumo marca "ArgentinaLuz" se hace un descuento del 40 % y si es de otra marca el descuento es del 30%.
- Si compra 4  lámparas bajo consumo marca "ArgentinaLuz" o “FelipeLamparas” se hace un descuento del 25 % y si es de otra marca el descuento es del 20%.
- Si compra 3  lámparas bajo consumo marca "ArgentinaLuz"  el descuento es del 15%, si es  “FelipeLamparas” 
se hace un descuento del 10 % y si es de otra marca un 5%.
Por otro lado, si el importe final con descuento suma más de $4000  se obtiene un descuento adicional de 5%.
Mostrar por pantalla: 
Marca, cantidad de lámparas, total a pagar sin descuento, el descuento obtenido si corresponde, 
el descuento adicional (si corresponde) y el total a pagar con descuento.
"""
# Definimos el precio base de las lámparas
precio_base = 800

# Solicitamos al usuario que ingrese la cantidad y marca de las lámparas
cantidad = int(input("Ingrese la cantidad de lámparas: "))
marca = input("Ingrese la marca de las lámparas: ")

# Calculamos el total a pagar sin descuento
total_sin_descuento = cantidad * precio_base

# Verificamos la cantidad y marca para aplicar el descuento correspondiente
if cantidad >= 6:
    descuento = 0.5  # 50% de descuento
elif marca == "ArgentinaLuz" and cantidad == 5:
    descuento = 0.4  # 40% de descuento
elif marca != "ArgentinaLuz" and cantidad == 5:
    descuento = 0.3  # 30% de descuento
elif marca == "ArgentinaLuz" or marca == "FelipeLamparas" and cantidad == 4:
    descuento = 0.25  # 25% de descuento
elif marca != "ArgentinaLuz" and marca != "FelipeLamparas" and cantidad == 4:
    descuento = 0.2  # 20% de descuento
elif marca == "ArgentinaLuz" and cantidad == 3:
    descuento = 0.15  # 15% de descuento
elif marca == "FelipeLamparas" and cantidad == 3:
    descuento = 0.1  # 10% de descuento
elif marca != "ArgentinaLuz" and marca != "FelipeLamparas" and cantidad == 3:
    descuento = 0.05  # 5% de descuento
else:
    descuento = 0  # No hay descuento

# Calculamos el descuento obtenido:
descuento_obtenido = total_sin_descuento * descuento

# Verificamos si el importe final con descuento suma más de $4000
if total_sin_descuento - descuento_obtenido > 4000:
    descuento_adicional = 0.05  # 5% de descuento adicional
else:
    descuento_adicional = 0  # No hay descuento adicional

# Calculamos el total a pagar con descuento
total_con_descuento = total_sin_descuento - descuento_obtenido - (total_sin_descuento - descuento_obtenido) * descuento_adicional

# Mostramos los resultados
print(f"Marca: {marca}")
print(f"Cantidad de lámparas: {cantidad}")
print(f"Total a pagar sin descuento: ${total_sin_descuento:.2f}")
print(f"Descuento obtenido: {descuento_obtenido:.2f}")
print(f"Descuento adicional: {descuento_adicional:.2f}")
print(f"Total a pagar con descuento: ${total_con_descuento:.2f}")
