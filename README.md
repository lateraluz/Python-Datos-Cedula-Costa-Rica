# Extraer información de la cédula de Costa Rica
Extrae la información contenida en el código PDF de la cédula de identidad de Costa Rica. Los datos que se puede leer son los siguientes:
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

## 4- Lógica 
La lógica para acceder la información es realizar un XOR entre el arreglo CONSTANTE [0x27, 0x30, 0x04, 0xA0, 0x00, 0x0F, 0x93, 0x12, 0xA0, 0xD1, 0x22, 0xE0, 0x03, 0xD0, 0x00, 0xDf, 0x00], con el arreglo de datos leído de la cédula en formato Hexadecimal.
El arreglo CONSTANTE es de 17 caracteres y el de datos de la cédula es mayor, por ello debe reiniciarse. 

``` Python
for byteFromArray in dataFromIdBytes:
    #Xor array to decrypt is 17 long bytes, reset when counter is 17
    if index == 17:
        index = 0

    caracter = xorOperation(keyBytes[index], byteFromArray);

    # From byte to char
    char_caracter = chr(caracter);

    # MUST include both letters and  numbers
    if re.match("^[a-zA-Z0-9]*$", char_caracter):
        data += char_caracter
    else:
        data += " "
    // increment index
    index = index + 1;
``` 



 
Feel free to improve it!

<BR>
<BR>
**knowledge belongs to humanity**, *Pascal*
