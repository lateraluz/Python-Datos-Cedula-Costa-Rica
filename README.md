# Cédula de Costa Rica
Extrae la información contenida en el código PDF de la cédula de identidad de Costa Rica para extraer:
1. Cédula
1. Nombre
1. Apellido
1. Sexo
1. Fecha nacimiento
1. Fecha de vencimiento

## 1- Escanear el dorso de la cédula SOLAMENTE el código PDF417
![1](https://user-images.githubusercontent.com/43474323/97226766-17679980-179a-11eb-8344-c274b5bdccfb.jpg)

## 2- Extraer la información.
Acceder a la página https://online-barcode-reader.inliteresearch.com/ y seguir los pasos.
![2](https://user-images.githubusercontent.com/43474323/97227753-8e516200-179b-11eb-8a0c-6c8b4824119d.png)

Nos interesa  la matriz de información señalada HASTA EL FINAL(La primer columna NO nos interes), ni lo demás caracteres al final   
![3](https://user-images.githubusercontent.com/43474323/97227766-90b3bc00-179b-11eb-818a-3a298708da80.png)

## 3- Formato de la Matrix
Los valores extraidos hay que darles formato en Hexadecimal.
![3](https://user-images.githubusercontent.com/43474323/97229186-93afac00-179d-11eb-81a0-35e9c55d8ed1.png)


## License
Feel free to improve it!

<BR>
<BR>
**knowledge belongs to humanity**, *Pascal*
