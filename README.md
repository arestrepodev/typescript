# Basic Course of TypeScript

## Tipado en TypeScript

### Explícito:

Define una sintaxis para la creación de variables con tipo de dato.

### Definición Post Fija:

`variableName : dataType`

### nomVariable:

Tipo de dato.

### Inferido:

TypeScript tiene la habilidad de "deducir" el tipo en funcion de un valor.

## Tipo de datos en JavaScript

- Number > Boolean > String > Array
- Tuple > Enum > Any > Void
- Null > Undefined > Never > Object

### Tipo: Number

- Valores Numéricos
- Valores Hexadécimales
- Valores Biarios
- Valores Hoctales

### Tipo: Boolean

- El tipo de dato más simple en TypeScript
- Dos únicos valores: true y false

### Tipo: Any

- Usado para capturar valores dinámicos
- Los valores pueden cambar de tipo en el tiempo:
  - APIs Externas
  - Librerias de Terceros

### Tipo: Void

- Es lo opuesto de any: representa la ausencia de tipo.
- Comúnmente se usa como tipo de retorno en funciones

### Tipo: Never

- Representa el tipo de valor que nuna ocurre
  - Funciones que lanzan exepctiones
  - Funciones que nunca retornan un valor

### Tipo: Undefined y Null

- En TypeScript, ambos "valores" tienen sus respectivos tipos:
  - Null
  - Undefined

#### Tipo: Undefined y Null (Subtipos)

- `Null y Undefined` se pueden asumir como subtipos de los otros tipos de datos
- Significa que se puede signar `null` y `undefined` a una variable de tipo `string`, por ejemplo.
- La opción `--strictNullChecks` nos permite asignar `null` o `undefined` a una variable de tipo `any` o sus respectivos tipos -`--strictNullChecks` Ayuda a evitar errores comunes en programación de apps en el ámbito de JavaScript.

```Bash
  $tsc --watch src/main.ts --strictNullChecks
```

```JSON
// Archivo de Configuración tsonfig.json

"strict": true
"strict": false

"strictNullChecks": true
"strictNullChecks": false
```

### Tipo: Object

- `object` es el tipo de dato que representa un valor no primitivo
- Es el tipo para cualquier variable que no sea number, string, boolean, null, undefined, etc

#### Object vs object

- `Object`: instancia de la clase Object de la clase de JavaScript
- `object`: Tipo para valores no primitivos. Con este tipo no se puede acceder a las propiedades de un objeto

### Tipo: Array

- Al igual que JavaScript, TypeScript permite definir un arreglo para contener un conjunto de valores.
- Usa dos notaciones: `[]` y `Array<tipo>`

### Tipo: Tupla

- Una tupla en TypeScript es un array de elementos que están tipados. De esta manera cada vez que haya que insertar un elemento se validará que dicho elemento coincida con el tipo de dato establecido en la tupla.
- Las tuplas permiten expresar un arreglo con un número fijo de elementos
- Los tipos de datos son conocidos

### Tipo: Enum

- Los enumerados permiten definir un conjunto de constantes con nombre
- Tienen la ventaja de adaptarse al contexto de la aplicación

### Unión de Tipos, Alias y Tipos Literales

- En TypeScript se puede definir una variable con múltiples tipos de datos: Union Type
- Se usa el símbolo de _pipe_ `("|")` entre los tipos

#### Alias de Tipos

- TypeScript permite crear alias como nuevo nombre para un tipo
- El alias de puede aplicar también a un conjunto o combinación de tipos
- Se usa la palabra reservada `type`

#### Literal Types

- Una variable con un tipo literal puede contener únicamente una cadena del conjunto.
- Se usan cadenas como "tipos" combinados con el símbolo de pipe '|' entre ellos

### Type Assertions

- Cuando un programados puede conocer más que TypeScript sobre el valor de una variable
- Es un mensaje al compilador: "Confía en mí, se lo que hago"
- Se parece al casting de tipos en otros lenguaje de programación
- Usa dos sintaxis: `<Angle Bracket>` y `(variable as type)`
