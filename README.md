#  GRÁFICO DE BARRAS AGRUPADAS PARA BASES DE DATOS
agrupar_por='HomeTeam' # La variable que me interesa agrupar en el gráfico de barras
columna_interes='FTR'  # La variable de interes
columna_referencia='Date' # La variable a la cual se le aplica la función de agregación

# Tabla pivote o tabla cruzada:
tabla = df.pivot_table(index=agrupar_por, columns=columna_interes, values=columna_referencia, aggfunc="count")

ax = tabla.plot(
                kind="bar", # Tipo de gráfico: bar chart
                figsize=(10,6), # Tamaño (m,n) m: ancho, n: alto
                fontsize=12, #Tamaño de letra
                ylim=(0,16), # Límite superior e inferior para el eje 'y'
                yticks=[2,5,8,11,14], # Líneas horizontales
                rot=90, # Inclinación de las etiquetas en grados
                colormap='Paired', # Colección de colores
                stacked=False, # barras apiladas: True, False
                )

ax.set_title('Gráfico de barras agrupadas', # Título del gráfico
             fontsize=20, # Tamaño de letra del título
             loc='right') # Localización del título: 'left' 'center' 'right'
ax.set_xlabel('Grupos', fontsize=12) # Nombre del eje 'x' y tamaño de letra
ax.set_ylabel('Frecuencia', fontsize=12) # Nombre del eje 'x' y tamaño de letra
ax.legend(['visitante', 'empate', 'local'], fontsize=12)

ax.grid(axis='y',          # Maya del eje 'y'
        color='gray',      # Color de la maya en eje 'y'
        linestyle='--',    # Estilo de línea
        linewidth=0.5)     # Ancho de línea

ax.grid(axis='x', linewidth=0)  
tabla
FTR	A	D	H
HomeTeam			
Alaves	4	8	7
Ath Bilbao	2	8	9
Ath Madrid	1	3	15
Barcelona	1	3	15
Betis	6	5	8
Celta	6	5	8
Eibar	4	6	9
Espanol	5	3	11
Getafe	5	3	11
Girona	10	6	3
Huesca	8	6	5
Leganes	4	8	7
Levante	6	7	6
Real Madrid	5	1	13
Sevilla	4	3	12
Sociedad	6	6	7
Valencia	2	10	7
Valladolid	9	5	5
Vallecano	8	6	5
Villarreal	6	8	5
