# Calculadora-de-Horas-trabajadas
#Programa en python para calcular el total de horas semanales trabajadas por un empleado


#DANIEL EDUARDO ROJAS FERIS
#GRUPO 213022_137
#INGENIERIA DE SISTEMAS
#Codigo fuente: Autoria Propia


# Función para calcular horas y clasificación
def calcular_horas(horas):

    total = sum(horas)

    if total > 40:
        clasificacion = "Sobretiempo"
    else:
        clasificacion = "Horario Estándar"

    return total, clasificacion


# matriz vacía
recursos = []

# Pedir cantidad de recursos
cantidad = int(input("Ingrese la cantidad de recursos: "))

# Días de la semana
dias = ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes"]

# Ingreso de datos
for i in range(cantidad):

    print("\nRecurso", i + 1)

    nombre = input("Ingrese el nombre del recurso: ")

    horas = []

    # Pedir horas por cada día
    for dia in dias:

        hora = float(input(f"Ingrese horas trabajadas el {dia}: "))
        horas.append(hora)

    # Guardar en la matriz
    fila = [nombre] + horas
    recursos.append(fila)


# Mostrar resultados
print("\n===== RESULTADOS =====")

for recurso in recursos:

    nombre = recurso[0]
    horas = recurso[1:]

    total, clasificacion = calcular_horas(horas)

    print("\nNombre:", nombre)
    print("Horas trabajadas:", horas)
    print("Total semanal:", total)

    print("Clasificación:", clasificacion)
