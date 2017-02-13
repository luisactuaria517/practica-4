# practica-4

### ejercicio

#### generar 4 objetos con datos aleatorios y que tenga 60 datos
#### objeto 1 d numero de profecionistas (mill) rango 5 a 8
#### objeto 2 crecimiento pib rango 0 a 5
#### objeto 3 porcentaje de ocupados de 40 a 60
#### objeto 4 porcentaje de ocupados de 3 a 8

prof<-sample(5:8,60, replace = T)
pib<-sample(0:5,60, replace = T)
por_ocu<-sample(40:60,60, replace = T)
por_des<-sample(3:8,60,replace = T)

# hacer data frame a los 4 objetos
pceu<-data.frame(prof, pib, por_ocu, por_des)

# mostrar los primeros 12 y los ultimos 12

pceu[1:12,]
pceu[48:60,]

# convertir los objetos en series de tiempo comenzando desde 
# el data frame comenzando 2010 y son datos mensuales

pceu_ts<- ts(pceu, frequency = 12, start = 2010)
pceu_ts

# graficar los prof y ocupados en la misma grafica

plot.ts(pceu_ts[,c(1,3)]) #hacer vector con c 

# graficar todas

plot.ts(pceu_ts)

# ts multiplie

pceu_ts

## base pib

pib_paises<-ts(read.csv(("C:\\Users\\luisa\\OneDrive\\Documentos\\r series de tiempo\\pib todos los paises.csv"), header = T), frequency = 1, start = 1980)
pib_paises
