# Actividad-U2
#ACTIVIDAD 2.1: simulación de operaciones bancarias 
import random

operacion = input("¿Que operación desea hacer: ingresar, retirar, abrir cuenta, cerrar cuenta o  consultar?")
operacion_limpia = operacion.lower().strip()
titular = "Ignacio Alvaro"
saldo = random.randint(0,1000)
estado =  True

match operacion_limpia:
    case "ingresar":
        cantidad = int(input("Dinero a ingresar: "))
        if cantidad > 0:
            saldo += cantidad
        else:
            print("Cantidad no valida")

    case "retirar":
        cantidad = int(input("Dinero a retirar: "))
        if cantidad > 0 and saldo >= cantidad:
            saldo -= cantidad
        else:
            print("Cantidad no valida")

    case "Abrir":
        if not estado:
            etado = True
        else:
            print("La cuenta ya está activa")

    case "cerrar":
        if estado and saldo == 0:
            estado = False
            print("Cuenta cerrada")
        else:
            print("La cuenta ya está cerrada")
            
    case "consultar":
        print(titular, "tu saldo es: ", saldo)
        
    case _:
        print("Operación no valida")
