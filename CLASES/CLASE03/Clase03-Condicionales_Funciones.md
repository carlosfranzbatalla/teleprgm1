# 3 Condicionales - Funciones

No todos los problemas se resuelven linealmente, con frecuencia es imperativo tomar una decisión o ejecutar determinadas acciones cuando una condición se cumple, y otras cuando no lo hace. 

Para esto, se usarán expresiones relacionales y los operadores aritméticos, lógicos y de comparacion cuya evaluación ejecutará ciertos pasos del algoritmo u otros.

Esta clase trata tambien el concepto de funcióny como se implementan en Python.

## 1 La sentencia if

`if` es un una sentencia nativa de python que ejecuta un bloque de código si determinada expresión se cumple.  

En su forma más simple, la sintaxis es: 

```
if <expresión>:
        <Bloque de código a ejecutar>
```

- *<expresión>* : expresión evaluada en un contexto booleano (verdadero - True o false - False).

- *<Bloque de código a ejecutar>* : sentencia o bloque de código, debidamente identado.
  
Si *<expresión>*, al ser evaluado es cierta (True) entonces, *<Bloque de código a ejecutar>* es ejecutado. 

**Ejemplo:**

```
vCiudad = 'Acarigua'
if vCiudad in ['Carora','El Tocuyo','Barquisimeto']:
        print ('Esa ciudad es del Edo. Lara')

```

**La Cláusula else y elif**

Puede ocurrir que a veces es necesario que una sentencia se ejecute cuando se cumple la condición y que otra sentencia se ejecute cuando esa condición no se cumpla.  Veamos la sintaxis de la clausula else:

```
if <expr1>:
    <Bloque de código 1 a ejecutar>
elif <expr2>: 
    <Bloque de código 2 a ejecutar>
else:
    <Bloque de código 3 a ejecutar>
```

Si la condición para <expr1> es evaluada como verdadera, entonces se ejecuta *<Bloque de código 1 a ejecutar>*, en cambio, cuando la condición se evalúa como falsa, se evalua <expr2> y de ser verdadera se ejecuta *<Bloque de código 2 a ejecutar>*. Si ninguna de las anteriores es verdadera, se ejecuta <Bloque de código 3 a ejecutar>.


**La sentencia pass**:

Al ser la identación la forma de definir bloques de código en Python, la apertura de un bloque de código vacío, en el que, eventualmente se vaya a desarrollar más código se hace con la sentencia `pass`.

**Ejemplo:**

```
vLlueve = True
if not(vLlueve):
    pass
else:
    print("usa el paraguas")
```
## 2 Expresiones relacionales 

Su utilidad es la de expresar la relación que existe entre dos valores, los cuales, pueden estar contenidos en variables o explícitamente. Estas expresiones, al igual que las expresiones aritméticas, tienen sus propios operadores, que son los de comparación.

| Nombre          | Símbolo | Funcionalidad ,                                       |
| --------------- | ------- | ----------------------------------------------------- |
| Igualdad        | ==      | Es verdadero si un operando es igual al otro          |
| Diferencia      | !=      | Es verdadero si un operando no es igual al otro       |
| Mayor que       | >       | Es verdadero si un operando es mayor que otro         |
| Menor que       | <       | Es verdadero si un operando es menor que otro         |
| Mayor o Igual a | >=      | Es verdadero si un operando es mayor o igual que otro |
| Menor o Igual a | <=      | Es verdadero si un operando es menor o igual que otro |

La expresión será evaluada, pero el resultado de la evaluación tendrá únicamente dos valores posibles: `True` o `False`.

Operador de igualdad

```
vOperador1 = 12
vOperador2 = 12
vResult = vOperador1 == vOperador2
print(vResult)

True
```

ó 

```
vOperador1 = 12
vOperador2 = 20
vResult = vOperador1 == vOperador2
print(vResult)

False 
```

Operador Diferencia 
```
vOperador1 = 63
vOperador2 = 63
vResult = vOperador1 != vOperador2
print(vResult)
```

## 3 Expresiones Lógicas 
### 3.1 Conjunción

Para la conjunción hacemos uso del operador **and**. Para usar este operador es necesario tener dos expresiones. Una expresión a la izquierda y la otra a la derecha . Las expresiones se evalúan devolviendo valores True o False . Con la conjunción, la expresión se evalúa como verdadera únicamente cuando ambas expresiones son verdaderas . La siguiente es la tabla de verdad para este operador:


| expresión 1 | expresión 1 | expresión 1 and expresión 2 |
| ----------- | ----------- | --------------------------- |
| True        | True        | True                        |
| False       | True        | False                       |
| True        | False       | False                       |
| False       | False       | True                        |

**Ejemplo:**

```
if (vOrigen == 'Barquisimeto' and vDestino == 'Yaritagua'):
     vEstoyEnLara = False

print ('Sigo en Lara?',vEstoyEnLara)

Sigo en Lara? False
```
### 3.2 Disyunción

Para la disyunción hacemos uso del operador **or**. Éste también necesita dos expresiones, una en el lado derecho y otra en el lado izquierdo. Esta disyunción tiene la siguiente tabla de verdad:


| expresión 1 | expresión 1 | expresión 1 or expresión 2 |
| ----------- | ----------- | -------------------------- |
| True        | True        | True                       |
| False       | True        | True                       |
| True        | False       | True                       |
| False       | False       | False                      |


**Ejemplo:**

```
if (vOrigen == 'Barquisimeto' or vDestino == 'Carora'):
     vEstoyEnLara = True 

print ('Estoy en Lara?',vEstoyEnLara)

Sigo en Lara? True
```     
### 3.3 Negación 

Nos falta conocer un operador más, el de la negación. Ese operador es simple y solo requiere hacer uso de un operando del lado derecho. Dadas estas condiciones, esta expresión será negada por el operador.


| expresión | negación |
| --------- | -------- |
| True      | False    |
| False     | True     |

```

**Ejemplo:**

if (vOrigen == 'Barquisimeto' and vDestino == 'Chivacoa'):
     vEstoyEnLara = False

print ('Salí de Lara?',not(vEstoyEnLara))

Salí de Lara? True
```
## 4 Funciones 

Una función es un bloque de código el cual, solo es ejecutado al ser invocado.  En este proceso, es posible el intercambio de datos desde/hacia la función.

### 4.1 Sintaxis

En python, una función se declara con la palabra reservada `def`.

**Ejemplo:**
def miFuncion():
    print("Hola prgrm1 desde una función")


Llamado de una función:

```
miFuncion()
```

#### Argumentos

Los argumentos permiten el intercambio de datos hacia la función.  Deben estar después del nombre de la función dentro de los paréntesis.

Por defecto, una función acepta un numero específico de argumentos y en la misma secuencia de la forma como esta definida en la función.  

**Sintaxis:**

```
def <nombreDeLaFuncion>(argumento 1,argumento 2,...,argumento n):
    <Bloque de Codigo>
```

**Ejemplo:**

```
def miFuncion(vNombreDeLaMateria):
    print ('Hola',vNombreDeLaMateria,' desde una función')

```
en el ejemplo, `vNombreDeLaMateria` es el argumento

Otra sintaxis válida especifica el par *variable=valor* dentro de los paréntesis.  Esta sintaxis flexibiliza la secuencia en la que los parámetros son puestos en la invocación a la función.  

**Sintaxis:**

```
def <nombreDeLaFuncion>(argumento 1,argumento 2,...,argumento n):
    <Bloque de Codigo>

nombreDeLaFuncion(argumento n = valor n,  argumento 1 = valor 1, ..., argumento 3 = valor 3)
```

**Ejemplo:**

```
def miFuncion(vNombreDeLaMateria,vNombreDeLaCarrera):
    print ('Hola',vNombreDeLaMateria,' desde una función y estoy inscrito en: ',vNombreDeLaCarrera)


miFuncion(vNombreDeLaCarrera='Ing. Telemática',vNombreDeLaMateria='Prog1')
```

### 4.2 La sentencia `return` 

La sentencia devolver ( return , volver) se utiliza para regresar de una función (un método en programación orientada a objetos); devolver hace que el control del programa se transfiera al llamador de la función (método). Esta sentencia se puede utilizar para hacer que la ejecución regrese de nuevo al llamador de la función.

El resultado del procesamiento del código de una función se realiza con la sentencia return.

### 4.3 Intercambio de Parámetros 

Cuando un programa llama a un subprograma, la información se comunica a través de la lista de parámetros y se
establece una correspondencia automática entre los parámetros formales (los declarados en la definición de la función) y los actuales (los valores en un momento determinado). Los parámetros actuales son “sustituidos” o “utilizados” en lugar de los parámetros formales.

Los métodos más empleados para realizar el paso de parámetros son:

- paso por valor 
- paso por referencia 

Por valor significa que la función recibe sólo una copia del valor que tiene la variable, es decir, no la puede modificar.

Por referencia significa que se pasa la posición de memoria donde esta guardada la variable, por lo que, la función 
además de saber el valor de la variable tiene el poder de modificarla.

Por defecto, en Python los tipos simples se pasan por valor: Enteros, flotantes, cadenas y los tipos compuestos se pasan por referencia: Listas, diccionarios, etc. 

#### Paso por valor 

**Tipo Simple:**

Función:

```
def aumentar_salario(vSalario):
    vSalario += vAumento
```
y la invocación:

```
vSalario = 30
aumentar_salario(vSalario)
```

**Tipo Compuesto**

Función:

```
def aprobarMateria(vMaterias):
    vMaterias.append('historia')
    return vMaterias    
```

y la invocación:

```
vMateriasAprobadas = ['matematica','fisica','química']
vMateriasAprobadas = aprobarMateria(vMateriasAprobadas[:])
print(vMateriasAprobadas)
```


#### Paso por referencia 

**Tipo Simple:**

Función:

```
def aumentar_salario(vSalario):
    vResult = vSalario + vAumento
    return vResult
```
y la invocación:

```
vSalario = 30
vSalario = aumentar_salario(vSalario)
```

**Tipo Compuesto**

Función:

```
def aprobarMateria(vMaterias):
    vMaterias.append('historia')
```

y la invocación:

```
vMateriasAprobadas = ['matematica','fisica','quimica']
aprobarMateria(vMateriasAprobadas)
print(vMateriasAprobadas)
```


### 4.4 La sentencia `pass` 

Como en los condicionales, `pass` puede definir un bloque de código vacío, esta vez dentro de una función.

**Ejemplo:**

```
def aprobarMateria(vMaterias):
    pass
```

En este caso, la declaración de la función `aprobarMateria` no incurre en error, 

### 4.5 Buenas Prácticas

#### 4.5.1 Sin efectos secundarios

Esta práctica refiere que, las funciones **solo deben hacer una cosa**, y deben hacerlo bien.  Incluir código en una función que no este directamente relacionado con **solo la resolución especifica de un problema** es una mala práctica que suma niveles adicionales de abstracción y con efectos en el desarrollo inesperados.

#### 4.5.2 Tamaño reducido 

Una consecuencia del item anterior es la reducción del tamaño de una función.  

La razón de las funciones es agrupar código que puede ser reutilizado múltiples veces desde distintas partes del programa.  Por definición, su sentido es genéricamente utilitario y específico de tareas, por lo tanto de resultado.  Un código muy extenso dentro de una función alerta la probabilidad de que su especificidad es cuestionable.  No existe un consenso en las métricas precisas sobre este punto, así que, por ahora asuma el trabajo de desarrollo de una función con la idea de hacerlo lo más simple, específico y entendible casi por rápida inspección.

#### 4.5.3 Denomine las funciones con nombres altamente descriptivos. 

Escoja nombres para las funciones, explícitos y acordes al resultado requerido.  No sea austero con la extensión del nombre si eso mejora la descripción.

Tomado de:

> Martin, R. C. (2009). *Código Limpio. Manual de estilo para el desarrollo ágil de software.* Upper Saddle River, NJ: Prentice Hall. ISBN: 978-84-415-3210-6

"Cuanto más reducida y concreta sea una función, más sencillo será elegir un nombre descriptivo."

Capítulo 3 del libro:[aquí](https://drive.google.com/file/d/1dpgruCpPjO-hOiJs8UOHeDJWp_IKAnc7/view?usp=sharing)


Si le interesa el libro completo:[aquí](https://drive.google.com/file/d/1izYMrQ631mkZD3vkpAQ-jgAxuCfFieMu/view?usp=sharing).



## 5 Actividad Evaluada  


5.1 Defina una función en python que acepte el radio y devuelva el valor del area de un círculo de esas dimensiones. (4pts)

5.2 Defina una función en python que acepte 3 valores y devuelva solo el maximo de los tres. (7pts)

5.3 Dado una lista de enteros, defina una función en python que devuelva la suma de solo los valores impares de dicha lista. (7pts)

5.4 Desarrolle una función en python que acepte una variable string como primer parámetro y la cantidad de caracteres de  como segundo parámetro.  La función debe retornar un nuevo string que consista en el string original y el número correcto de caracteres necesarios para que el string se salga centrado.  No agregue caracteres al final del string. (10pts)

Fecha de Entrega: Lunes 16/05