from os import system
system("cls")

Enfermos=[]

def menu():
    print("[1] Ingresar paciente")
    print("[2] Modificar paciente")
    print("[3] Eliminar paciente")
    print("[4] Consultar paciente")
    print("[5] Listar pacientes")
    print("[6] Listar actividades")
    print("[7] Ingrese las actividades de un paciente")
    print("[8] paciente mas joven")
    print("[9] paciente mas viejo")
    print("[10] paciente que mas veces realizo una actividad")
    print("[0] Salir")
    opcion=int(input("Ingrese una opcion: "))
    return opcion

def ingresar_paciente(Enfermos):
    nombre = input("Ingrese el nombre del paciente: ")
    apellido = input("Ingrese el apellido del paciente: ")
    dni = input("Ingrese el dni del paciente: ")
     edad = int(input("Ingrese la edad del paciente: "))
    telefono = input("Ingrese el telefono del paciente: ")
    direccion = input("Ingrese la direccion del paciente: ")
    paciente = {"nombre":nombre,
            "apellido":apellido,
            "dni":dni,
            "edad":edad,
            "telefono":telefono,
            "direccion":direccion,
            "actividades":[]}
    Enfermos.append(paciente)
    return Enfermos

def modificar_paciente(paciente):
    dni=input("Ingrese el dni del paciente a modificar: ")
    for paciente in Enfermos:
        if paciente["dni"]==dni:
            paciente["nombre"]=input("Ingrese el nombre del paciente: ")
            paciente["apellido"]=input("Ingrese el apellido del paciente: ")
            paciente["edad"]=int(input("Ingrese la edad del paciente: "))
            paciente["telefono"]=input("Ingrese el telefono del paciente: ")
            paciente["direccion"]=input("Ingrese la direccion del paciente: ")
            paciente["actividades"]=[]
            return Enfermos
    print("No se encontro el paciente")
    return Enfermos

def eliminar_paciente(Enfermos):
    dni=input("Ingrese el dni del socio a eliminar: ")
    for paciente in Enfermos:
        if paciente["dni"]==dni:
            Enfermos.remove(paciente)
            return Enfermos
    print("No se encontro el paciente")
    return Enfermos

def consultar_paciente(Enfermos):
    dni=input("Ingrese el dni del paciente a consultar: ")
    for paciente in Enfermos:
        if paciente["dni"]==dni:
            print("Nombre: ",paciente["nombre"])
            print("Apellido: ",paciente["apellido"])
            print("Edad: ",paciente["edad"])
            print("Telefono: ",paciente["telefono"])
            print("Direccion: ",paciente["direccion"])
            print("Actividades: ",paciente["actividades"])
            return
    print("No se encontro el socio")
    return

def listar_Enfermos(paciente):
    for paciente in Enfermos:
        print("Nombre: ",paciente["nombre"])
        print("Apellido: ",paciente["apellido"])
        print("Edad: ",paciente["edad"])
        print("Telefono: ",paciente["telefono"])
        print("Direccion: ",paciente["direccion"])
        print("Actividades: ",paciente["actividades"])
        print("-------------------------------")
    return

def listar_actividades(Enfermos):
    actividades=[]
    for paciente in Enfermos:
        for actividad in paciente["actividades"]:
            if actividad not in actividades:
                actividades.append(actividad)
    for actividad in actividades:
        print(actividad)
    return

def ingresar_actividades(Enfermos):
    dni=input("Ingrese el dni del paciente: ")
    for paciente in Enfermos:
        if paciente["dni"]==dni:
            actividad=input("Ingrese la actividad: ")
            paciente["actividades"].append(actividad)
            return Enfermos
    print("No se encontro el paciente")
    return Enfermos

def paciente_mas_joven(Enfermos):
    paciente_mas_joven=Enfermos[0]
    for paciente in Enfermos:
      if paciente["dni"]==dni:
            actividad=input("Ingrese la actividad: ")
            paciente["actividades"].append(actividad)
            return Enfermos
    print("No se encontro el paciente")
    return Enfermos

def paciente_mas_joven(Enfermos):
    paciente_mas_joven=Enfermos[0]
    for paciente in Enfermos:
        if paciente["edad"]<paciente_mas_joven["edad"]:
            paciente_mas_joven=paciente
    print("Nombre: ",paciente_mas_joven["nombre"])
    print("Apellido: ",paciente_mas_joven["apellido"])
    print("Edad: ",paciente_mas_joven["edad"])
    print("Telefono: ",paciente_mas_joven["telefono"])
    print("Direccion: ",paciente_mas_joven["direccion"])
    print("Actividades: ",paciente_mas_joven["actividades"])
    return paciente_mas_joven

def paciente_mas_viejo(Enfermos):
    paciente_mas_viejo=Enfermos[0]
    for paciente in Enfermos:
        if paciente["edad"]>paciente_mas_viejo["edad"]:
            paciente_mas_viejo=paciente
    print("Nombre: ",paciente_mas_viejo["nombre"])
    print("Apellido: ",paciente_mas_viejo["apellido"])
    print("Edad: ",paciente_mas_viejo["edad"])
    print("Telefono: ",paciente_mas_viejo["telefono"])
    print("Direccion: ",paciente_mas_viejo["direccion"])
    print("Actividades: ",paciente_mas_viejo["actividades"])
    return paciente_mas_viejo

def paciente_mas_actividades(Enfermos):
    paciente_mas_actividades=Enfermos[0]
    for paciente in Enfermos:
        if len(paciente["actividades"])>len(paciente_mas_actividades["actividades"]):
            paciente_mas_actividades=paciente
    print("Nombre: ",paciente_mas_actividades["nombre"])
    print("Apellido: ",paciente_mas_actividades["apellido"])
    print("Edad: ",paciente_mas_actividades["edad"])
    print("Telefono: ",paciente_mas_actividades["telefono"])
    print("Direccion: ",paciente_mas_actividades["direccion"])
    print("Actividades: ",paciente_mas_actividades["actividades"])
    return paciente_mas_actividades

def main():
    
    Enfermos=[]
    opcion=menu()
    edad=int(input('Que edad tiene?'))
    
    if edad > 18:  
        while opcion!=0:
            if opcion==1:
                Enfermos=ingresar_paciente(Enfermos)
            elif opcion==2:
                Enfermos=modificar_paciente(Enfermos)
            elif opcion==3:
                Enfermos=eliminar_paciente(Enfermos)
            elif opcion==4:
                consultar_paciente(Enfermos)
            elif opcion==5:
                listar_Enfermos(Enfermos)
            elif opcion==6:
                listar_actividades(Enfermos)
            elif opcion==7:
                socios=ingresar_actividades(Enfermos)
            elif opcion==8:
                paciente_mas_joven(Enfermos)
            elif opcion==9:
                paciente_mas_viejo(Enfermos)
            elif opcion==10:
                paciente_mas_actividades(Enfermos)
            else:
                print("Opcion incorrecta")
            opcion=menu()
        return 

    else:
        print('Es menor de edad. No puede seguir')
main()
