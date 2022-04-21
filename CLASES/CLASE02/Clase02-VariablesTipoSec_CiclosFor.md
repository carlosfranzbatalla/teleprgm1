# 2 Variables Tipo Secuencia - Ciclos

## 1 Variables Tipo Secuencia

### 1.1 Listas

En python, una variable tipo Lista, sirve para almacenar multiples valores, encerrandolos en corchetes y separando c/u de estos valores con comas, asi:

```
vPrimeraLista = ['a','laptop','dcyt']
```

o

```
vDecanatos = ['agronomia','ciencias economicas','ciencias y tecnologia','ciencias veterinarias','humanidades']
vMedidas = [23,3,52]
```

y puede combinar distintos tipos de datos, asi:

```
vDatosdDelFilosofo = ["Immanuel Kant", 17240422, 18040212, "Crítica de la razón pura","La libertad es aquella facultad que aumenta la utilidad de todas las demás facultades."]
```

Entonces, una lista en Python es una estructura de datos formada por una secuencia ordenada de valores.

#### 1.1.1 Índice de una lista

Los elementos de una lista pueden accederse mediante su índice, que leidos desde izquierda a derecha (índices positivos) tiene como primer elemento el 0.  Si son leidos desde la derecha a la izquierda (índices negativos) empieza con -1.

Veámoslo con la lista de los minerales:

```
vDecanatos = ['agronomia','ciencias economicas','ciencias y tecnologia','ciencias veterinarias','humanidades']
```

|`vDecanatos=`  | `['agronomia',` |`'ciencias economicas',` |`'ciencias y tecnologia',` |`'ciencias veterinarias',` |` 'humanidades'] `|
|:-----------------:|:--------:|:-------:|:--------:|:--------:|:--------:|
| índices positivos |     0    |    1    |     2    |     3    |     4    |
| índices negativos |    -5    |    -4   |    -3    |    -2    |    -1    |

El acceso a los elementos singulares de una lista se hace con la sintaxis:

`<Lista>[indice]`

Así, si desea obtener el valor el tercer elemento de la lista:

```
print ("el tercer elemento de la lista es: ",vDecanatos[2])
el tercer elemento de la lista es:  ciencias y tecnologia
```

#### 1.1.2 Sublistas

Python le provee esta sintaxis para definir sublistas: `<desde>:<hasta>:<paso>`

- `<desde>`: La sublista incluye el valor que corresponde al índice. Si no especifica un valor, python asume por defecto 0.

- `<hasta>`: Índice que indica el tope de la sublista. No incluye el valor que corresponde al índice.

- `<paso>`: Toma un valor cada Si no especifica un valor, python asume por defecto 1.

Ejemplos:

```
print (vDecanatos[1:3])
['ciencias economicas', 'ciencias y tecnologia']
```

con índices negativos:

```
print (vDecanatos[-5:-3])
['agronomia', 'ciencias economicas']
```

#### 1.1.3 Modificando los valores de una lista

Use el indice para la modificación singular de un valor de la lista.  La sintaxis es la siguiente:

`<Lista>[indice] = <valor>`

```
vDecanatos[4] = 'ingenieria civil'

print(vDecanatos)
['agronomia', 'ciencias economicas', 'ciencias y tecnologia', 'ciencias veterinarias', 'ingenieria civil']
```

o

```
vDecanatos[-5] = 'ingenieria civil'

print(vDecanatos)
['ingenieria civil', 'ciencias economicas', 'ciencias y tecnologia', 'ciencias veterinarias', 'ingenieria civil']
```

**modificación por rangos:**

Defina una lista que reemplazará el rango que desee modificar.

Ejem.:

```
vDecanatos[2:4]=['agronomia','humanidades']
print(vDecanatos)
['ingenieria civil', 'ciencias economicas', 'agronomia', 'humanidades', 'ingenieria civil']
```

Tenga en cuenta:

- si incluye más valores a cambiar que el especificado en la lista, el excedente de los valores se insertan.
- si incluye menos valores a cambiar que el especificado en la lista, el excedente de la lista se suprime.

**Métodos sobre una lista:**

1. *append*

Agrega un valor como último elemento de la lista.

```
vDecanatos = ['agronomia','ciencias economicas','ciencias y tecnologia','ciencias veterinarias','humanidades']
vDecanatos.append('ingenieria civil')
print(vDecanatos)

['agronomia', 'ciencias economicas', 'ciencias y tecnologia', 'ciencias veterinarias', 'humanidades', 'ingenieria civil']
```

2. *insert*

Inserta un valor en una posición específica:

```
vDecanatos.insert(1,'ciencias de la salud')
print(vDecanatos)
['agronomia', 'ciencias de la salud', 'ciencias economicas', 'ciencias y tecnologia', 'ciencias veterinarias', 'humanidades', 'ingenieria civil']
```

3. *remove*

eliminación por valor

```
print(vDecanatos)
['agronomia', 'ciencias de la salud', 'ciencias economicas', 'ciencias y tecnologia', 'ciencias veterinarias', 'humanidades', 'ingenieria civil']

vDecanatos.remove('agronomia')

print(vDecanatos)

['ciencias de la salud', 'ciencias economicas', 'ciencias y tecnologia', 'ciencias veterinarias', 'humanidades', 'ingenieria civil']
```

eliminación por índice:

4. *pop*

```
vDecanatos.pop(4)
'humanidades'
print(vDecanatos)
['ciencias de la salud', 'ciencias economicas', 'ciencias y tecnologia', 'ciencias veterinarias', 'ingenieria civil']
```

5. *del*

```
['ciencias de la salud', 'ciencias economicas', 'ciencias y tecnologia', 'ciencias veterinarias', 'ingenieria civil']
del vDecanatos[1]
print(vDecanatos)
['ciencias de la salud', 'ciencias y tecnologia', 'ciencias veterinarias', 'ingenieria civil']
 ```

### 1.2 Tuplas

En python, una variable tipo Tupla, sirve para almacenar multiples valores, encerrandolos en parentesis y separando c/u de estos valores con comas, asi:

```
vPrimeraTupla = ('a','laptop','dcyt')
```

o

```
vTuplaDeDecanatos = ('agronomia','ciencias economicas','ciencias y tecnologia','ciencias veterinarias','humanidades')
```

Las tuplas son estructuras de datos similares a las listas, con la diferencia de que las tuplas son inmutables.  El intento de modificar algún valor de una tupla, producirá un error como el siguiente:

```
vTuplaDeDecanatos[1]='ingenieria civil'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

## 2 Ciclos. Iterando sobre una secuencia. La sentencia `for`

Un ciclo consiste en la ejecución repetida de un bloque de código hasta que, determinada condición es alcanzada.
Cada iteración sobre una secuencia es un ciclo.  

Recorrer c/u de los valores que componen una secuencia (variables tipo string, listas y/o tuplas) es posible con la sentencia for.

```
for <indice> in <secuencia>:
    <bloque de código>
```

Veamos como recorrer la lista vDecanatos:

```
vDecanatos = ['agronomia','ciencias economicas','ciencias y tecnologia','ciencias veterinarias','humanidades']
for vIndice in vDecanatos:
    print ("el decanato es: ",vIndice)
 
el decanato es:  agronomia
el decanato es:  ciencias economicas
el decanato es:  ciencias y tecnologia
el decanato es:  ciencias veterinarias
el decanato es:  humanidades
```

> la sentencia `for` se ejecutará item por item desde el elemento `[0]` hasta el final de la secuencia `len<secuencia>` sin necesidad de incluir una cláusula que interrumpa el proceso y asi evitar el ciclo infinito, como veremos con otras sentencias que manejan ciclos.  Sin embargo, puede introducir la directiva `break` en la lógica de su código si viese necesario interrumpir la ejecución del ciclo antes de llegar al último elemento.

## 3 Buenas Prácticas

### 3.1 Nombres de las variables

No tenga reparos en asignar nombres para las variables que sea los más explicita y demostrativo posible respecto al sentido que esa variable va a representar dentro de su desarrollo.  

Es preferible el nombre `vDiasDeVacacionesRestantes` que `dias`.

Solo los nombres de las variables, funciones, clases, métodos etc. le darán al lector una muy buena idea de como su código resuelve el problema.

Las directivas que seguiremos en esta cátedra para la asignación de nombres, las obtendrá del capítulo 2 del libro:

> Martin, R. C. (2009). *Código Limpio. Manual de estilo para el desarrollo ágil de software.* Upper Saddle River, NJ: Prentice Hall. ISBN: 978-84-415-3210-6

[aquí](https://drive.google.com/file/d/1sPk-jalJA95Nk0v8ZyNcJ9KqqsCab7X0/view?usp=sharing)

Si le interesa el libro completo:[aquí](https://drive.google.com/file/d/1izYMrQ631mkZD3vkpAQ-jgAxuCfFieMu/view?usp=sharing).



## 4 Actividad Evaluada


- 4.1 Implemente una tupla de un solo elemento.  Tiene una particularidad, investigue. (2pts.)

- 4.2 Dada una lista de las edades de una población que ha ido a vacunarse, 

vEdades = [2, 7, 58, 7, 45, 26, 10, 8, 56, 57, 97, 19, 11, 53, 3, 99, 62, 78, 29, 9, 37, 42, 56, 86, 28, 86, 95, 26, 49, 67, 21, 815, 67, 10, 58, 512, 24, 92, 89, 67, 53, 10, 9, 83, 1, 44, 10, 77, 98, 73, 57]

Elimine de la lista, todas las ocurrencias del entero 10 (3pts)

**Fecha tope de entrega: lunes 28 de Marzo. 4:30pm.**
