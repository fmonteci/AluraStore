# AluraStore FM

# Challenge 1 DataScience

# 📢 Objetivo
El objetivo del proyecto es poder xtraer la información, realizar analisis de datos y gráficas para ayudar al Sr. Juan a decidir que tienda debe vender

# Extracción de datos
Carga de datos .CSV
```
import pandas as pd

url = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_1%20.csv"
url2 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_2.csv"
url3 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_3.csv"
url4 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_4.csv"

tienda = pd.read_csv(url)
tienda2 = pd.read_csv(url2)
tienda3 = pd.read_csv(url3)
tienda4 = pd.read_csv(url4)

tienda.head()

```

<img width="1207" height="167" alt="image" src="https://github.com/user-attachments/assets/7fa89f68-2183-4559-835c-fba0a03c1369" />

# 🔎 Análisis de Datos

## Ingresos por Tienda
:one: **Tienda 1**
* La facturación total de tienda 1 es de $1150880400.0
* La facturación promedio de tienda 1 es $487867.91
* Su media es mayor a la mediana por lo que se observa un sesgo a la derecha con posibles outliers.
* Su venta min es 7600 y su max 2977000.
* El 50% de su compras se encuentran entre los siguientes rangos q1: 55750.00 y q3: 678100.00.
* La facturación total de tienda2 es de $1116343500.0

  <img width="140" height="247" alt="image" src="https://github.com/user-attachments/assets/54783147-c8c6-46e0-aa84-f7321728ecdf" />

2️⃣ **Tienda 2**
* La facturación total de tienda 2 es de $1116343500.0
* La facturación promedio de tienda 2 es de $473227.43
* Su media es mayor a la mediana por lo que se observa un sesgo a la derecha con posibles outliers.
* Su venta min es de 7600 y su max es de 2953400.00.
* El 50% de su compras se encuentran entre los siguientes rangos q1: 54550.00 y q3: 677700.00
* la facturación total de tienda3 es de $1098019600.0

<img width="125" height="244" alt="image" src="https://github.com/user-attachments/assets/01e0660b-3be8-454c-b82a-a26e268dc909" />

3️⃣ **Tienda 3**
* La facturación total de tienda 3 es de $1098019600.0
* La facturación promedio de tienda 3 es de $465459.77
* Su media es mayor a la mediana por lo que se observa un sesgo a la derecha con posibles outliers.
* Su venta min es de 7600 y su max de 2968200.00.
* El 50% de su compras se encuentran entre los siguientes rangos q1: 57400.00 y q3: 666050.00
* la facturación total de tienda 4 es de $1038375700.0
  
<img width="143" height="243" alt="image" src="https://github.com/user-attachments/assets/66c07855-4f5e-4830-a788-1e4a53fb2e37" />

4️⃣ **Tienda 4**
* La facturación total de tienda 4 es de $1038375700.0
* La facturación promedio de tienda 4 es de $440362.89
* Su media es mayor a la mediana por lo que se observa un sesgo a la derecha con posibles outliers.
* Su venta min es de 7600 y su max de 2902200.00.
* El 50% de su compras se encuentran entre los siguientes rangos q1: 53400.00 y q3: 634225.00

<img width="154" height="242" alt="image" src="https://github.com/user-attachments/assets/2a231d7c-2873-41b6-8c8f-983d16fbd268" />

💵 Facturación por tienda

<img width="834" height="462" alt="image" src="https://github.com/user-attachments/assets/5f94731f-6098-4b81-928b-940279ee69ae" />


## 📚Ventas por Categoría
Análisis por cantidad de productos vendidos
* La categoria con mayor cantidad de productos vendidos en tienda 1 es muebles con 465 ventas y la categoria con menos cantidad de ventas es Artículos para el Hogar con 171 ventas. Cantidad de ventas totales 2359
* La categoria con mayor cantidad de productos vendidos en tienda 2 es muebles con 442 ventas y la categoria con menos cantidad de ventas es Artículos para el Hogar con 181 ventas. Cantidad de ventas totales 2359
* La categoria con mayor cantidad de productos vendidos en tienda 3 es muebles con 499 ventas y las categorias con menos cantidad de ventas son Artículos para el Hogar e Instrumentos Musicales con 177 ventas. Cantidad de ventas totales 2359
* La categoria con mayor cantidad de productos vendidos en tienda 4 es muebles con 480 ventas y la categoria con menos cantidad de ventas es Instrumentos Musicales con 170 ventas. Cantidad de ventas totales 2358
  
<img width="262" height="631" alt="image" src="https://github.com/user-attachments/assets/e1350fb4-24e0-4610-a9f2-b23d9cf3bdf4" />

```
conteo = tienda.groupby('Categoría del Producto').size().reset_index(name='Cantidad')
conteo2=tienda2.groupby('Categoría del Producto').size().reset_index(name='Cantidad')
conteo3=tienda3.groupby('Categoría del Producto').size().reset_index(name='Cantidad')
conteo4=tienda4.groupby('Categoría del Producto').size().reset_index(name='Cantidad')
print(conteo)
print(f"el maximo {max(conteo['Cantidad'])}, el min {min(conteo['Cantidad'])}")
print(f"***************************************\n {conteo2}")
print(f"el maximo {max(conteo2['Cantidad'])}, el min {min(conteo2['Cantidad'])}")
print(f"***************************************\n {conteo3}")
print(f"el maximo {max(conteo3['Cantidad'])}, el min {min(conteo3['Cantidad'])}")
print(f"***************************************\n {conteo4}")
print(f"el maximo {max(conteo4['Cantidad'])}, el min {min(conteo4['Cantidad'])}")
```

Top 5 Productos con Masyores ventas ( % del $ Total vendido)

<img width="1020" height="702" alt="image" src="https://github.com/user-attachments/assets/8ac32636-8af9-4388-9ec2-bb619ce0abfe" />

## 🎢 Productos más y menos vendidos

**Tienda 1**
* Los 3 Productos más vendidos son Microondas, TV Led Uhd 4k y Armario con 60 unidades vendidas cu.
* Los Productos menos vendidos son Auriculares con micrófono y Celular ABXY con 33 unidades vendidas cu.
  
<img width="1244" height="463" alt="image" src="https://github.com/user-attachments/assets/ae0743c0-54ca-4738-a24e-7b8d50850f68" />

**Tienda 2**
* El producto más vendido es Iniciando en programación con 65 unidades vendidas
* El producto Juego de mesa es el menos vendido con 32 unidades vendidas

<img width="1237" height="499" alt="image" src="https://github.com/user-attachments/assets/f6cd172b-1c62-435d-9c34-8acf8f9bacf4" />

**Tienda 3**
* El producto más vendido es Kit de bancas con 57 unidades vendidas
* El producto Bloques de construcción es el menos vendido con 35 unidades vendidas
  
<img width="1296" height="503" alt="image" src="https://github.com/user-attachments/assets/d35e4326-6dc4-4ba3-b03c-07eff21882cb" />


**Tienda 4** 
* El producto más vendido es Cama box con 62 unidades vendidas
* El producto Guitarra eléctrica es el menos vendido con 33 unidades vendidas
<img width="1256" height="487" alt="image" src="https://github.com/user-attachments/assets/eccb4ac9-3df5-454c-8448-29c66fcd99a9" />

## 🌟 Satisfacción por Tienda  
Se observa que las calificaciones promedio por tienda se encuentran muy proximas entre si, la diferencia se encuentra a nivel de centesima. Los valores en orden por tienda son
* Tienda 3, con una calificacion de **4.048**
* Tienda 2, con una calificacion de **4.037**
* Tienda 4, con una calificacion de **3.995**
* Tienda 1, con una calificacion de **3.976**

<img width="864" height="660" alt="image" src="https://github.com/user-attachments/assets/1a9da757-fa96-43ba-b490-57c9a06e0f67" />

```

fig, axs=plt.subplots(2,2, figsize=(10,8))
axs[0,0].hist(tienda["Calificación"], bins=5, label="Calificación")
axs[0,0].axvline(cal,color="red",linestyle="-", label="promedio")
axs[0,0].set_title("Histograma Satisfacción Tienda 1")
axs[0,0].legend()
axs[0,1].hist(tienda2["Calificación"], bins=5, label="Calificación")
axs[0,1].axvline(cal2,color="red",linestyle="-", label="promedio")
axs[0,1].legend()
axs[0,1].set_title("Histograma Satisfacción Tienda 2")
axs[1,0].hist(tienda3["Calificación"], bins=5, label="Calificación")
axs[1,0].axvline(cal3,color="red",linestyle="-", label="promedio")
axs[1,0].legend()
axs[1,0].set_title("Histograma Satisfacción Tienda 3")
axs[1,1].hist(tienda4["Calificación"], bins=5, label="Calificación")
axs[1,1].axvline(cal4,color="red",linestyle="-", label="promedio")
axs[1,1].legend()
axs[1,1].set_title("Histograma Satisfacción Tienda 4")
plt.tight_layout()
plt.show()

cal=tienda['Calificación'].mean()
cal2=tienda2['Calificación'].mean()
cal3=tienda3['Calificación'].mean()
cal4=tienda4['Calificación'].mean()

print(f"promedio tienda 1 {cal}\npromedio tienda 2 {cal2}\npromedio tienda 3 {cal3}\npromedio tienda 4 {cal4}")
```
## 💲Costo de Envío por Tienda
Observamos que la tienda con menor costo es la 4 con un valor de $23.459, en tanto que la mayor es la tienda 1 con un valor promedio de envío de $26.018.
el detalle de las tiendas a continuación:
* el costo de envio promedio de tienda 1 es: 26018.60958033065
* el costo de envio promedio de tienda 2 es: 25216.235693090293
* el costo de envio promedio de tienda 3 es: 24805.680373039424
* el costo de envio promedio de tienda 4 es 23459.457167090754

<img width="768" height="398" alt="image" src="https://github.com/user-attachments/assets/7db6c2e4-1d78-4dd7-9655-d6f9deb5b964" />
  
## 💵 Rentabilidad
Observando los ingresos totales menos el costo de envío para determinar la rentabilidad total de cada tienda. 
obtenemos el siguiente detalle:
* Rentabilidad Tienda 1: $1089502500.0
* Rentabilidad Tienda 2: $1056858400.0
* Rentabilidad Tienda 3: $1039503000.0
* Rentabilidad Tienda 4: $983058300.0

<img width="722" height="448" alt="image" src="https://github.com/user-attachments/assets/9d8499ee-4d10-4a37-8163-85a7206ffaba" />

# Recomendación
