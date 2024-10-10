
## Resultado

[Consultar](https://renegarcia.github.io/eleventa-db/) la base de datos Eleventa.

## Código


Primero instalamos el paquete `sqlparse`. Desde `pypy`:

```shell
pip install sqlparse
```

Si utlizamos `poetry`:

```shell
poetry add sqlparse
```

Una vez instalado, en una sesión de `python` lo podemos importar de la manera usual


```python
from typing import Optional
from sqlparse.sql import Statement
from sqlparse.tokens import Keyword
from dataclasses import dataclass
import sqlparse
```

## Extrayendo el nombre de una definición de tabla 

Vamos a utilizar el siguiente ejemplo de `SQL` para aprender a extraer la información que necesitamos


```python
TABLE = """CREATE TABLE IF NOT EXISTS MY_TABLE (ID TLLAVE NOT NULL,
    CONSTRAINT PK_MY_TABLE PRIMARY KEY (ID));
"""
```


```python
parsed = sqlparse.parse(TABLE) # Devuelve una tupla de statements sql contenidos en la cadena
statement = parsed[0]
```


```python
print(statement)
```

    CREATE TABLE IF NOT EXISTS MY_TABLE (ID TLLAVE NOT NULL,
        CONSTRAINT PK_MY_TABLE PRIMARY KEY (ID));


`statement` es una variable tipo `Statement` que puede ser iterada por medio de índices o ciclos.


```python
token = statement[0]
print(type(statement), type(token))
```

    <class 'sqlparse.sql.Statement'> <class 'sqlparse.sql.Token'>


Cada token define dos atributos: `value` y `ttype`, sin embargo el parser es flojo, al invocarlo evitará escanear recursivamente la cadena como se puede ver en los siguientes ejemplos.


```python
# En este caso, el primer token tiene un valor definido y un tipo.
token.value, token.ttype
```




    ('CREATE', Token.Keyword.DDL)




```python
# En este ciclo se puede ver que los tokens 11 y 13 no fueron analizados por el parser.
for i, token in enumerate(statement):
    token_type = repr(token.ttype)
    print(f"{i+1:2d}. {token.value:50} {token_type:50} {type(token)}")

```

     1. CREATE                                             Token.Keyword.DDL                                  <class 'sqlparse.sql.Token'>
     2.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
     3. TABLE                                              Token.Keyword                                      <class 'sqlparse.sql.Token'>
     4.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
     5. IF                                                 Token.Keyword                                      <class 'sqlparse.sql.Token'>
     6.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
     7. NOT                                                Token.Keyword                                      <class 'sqlparse.sql.Token'>
     8.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
     9. EXISTS                                             Token.Keyword                                      <class 'sqlparse.sql.Token'>
    10.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    11. MY_TABLE                                           None                                               <class 'sqlparse.sql.Identifier'>
    12.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    13. (ID TLLAVE NOT NULL,
        CONSTRAINT PK_MY_TABLE PRIMARY KEY (ID)) None                                               <class 'sqlparse.sql.Parenthesis'>
    14. ;                                                  Token.Punctuation                                  <class 'sqlparse.sql.Token'>


El método `Statement.flatten` realizará el parseo de la cadena completa, devolviendo los tipos y valores de cada token encontrado.


```python
for i, token in enumerate(statement.flatten()):
    token_type = repr(token.ttype)
    print(f"{i+1:2d}. {token.value:50} {token_type:50} {type(token)}")
```

     1. CREATE                                             Token.Keyword.DDL                                  <class 'sqlparse.sql.Token'>
     2.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
     3. TABLE                                              Token.Keyword                                      <class 'sqlparse.sql.Token'>
     4.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
     5. IF                                                 Token.Keyword                                      <class 'sqlparse.sql.Token'>
     6.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
     7. NOT                                                Token.Keyword                                      <class 'sqlparse.sql.Token'>
     8.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
     9. EXISTS                                             Token.Keyword                                      <class 'sqlparse.sql.Token'>
    10.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    11. MY_TABLE                                           Token.Name                                         <class 'sqlparse.sql.Token'>
    12.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    13. (                                                  Token.Punctuation                                  <class 'sqlparse.sql.Token'>
    14. ID                                                 Token.Name                                         <class 'sqlparse.sql.Token'>
    15.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    16. TLLAVE                                             Token.Name                                         <class 'sqlparse.sql.Token'>
    17.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    18. NOT NULL                                           Token.Keyword                                      <class 'sqlparse.sql.Token'>
    19. ,                                                  Token.Punctuation                                  <class 'sqlparse.sql.Token'>
    20. 
                                                      Token.Text.Whitespace.Newline                      <class 'sqlparse.sql.Token'>
    21.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    22.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    23.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    24.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    25. CONSTRAINT                                         Token.Keyword                                      <class 'sqlparse.sql.Token'>
    26.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    27. PK_MY_TABLE                                        Token.Name                                         <class 'sqlparse.sql.Token'>
    28.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    29. PRIMARY                                            Token.Keyword                                      <class 'sqlparse.sql.Token'>
    30.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    31. KEY                                                Token.Keyword                                      <class 'sqlparse.sql.Token'>
    32.                                                    Token.Text.Whitespace                              <class 'sqlparse.sql.Token'>
    33. (                                                  Token.Punctuation                                  <class 'sqlparse.sql.Token'>
    34. ID                                                 Token.Name                                         <class 'sqlparse.sql.Token'>
    35. )                                                  Token.Punctuation                                  <class 'sqlparse.sql.Token'>
    36. )                                                  Token.Punctuation                                  <class 'sqlparse.sql.Token'>
    37. ;                                                  Token.Punctuation                                  <class 'sqlparse.sql.Token'>


### Método para obtener el nombre de la tabla

Las tablas que nos interesa analizar todas tienen siempre la siguiente estructura 

```sql
CREATE TABLE [IF NOT EXISTS] my_table_name ...
```

por lo que para encontrar el nombre de la tabla necesitamos encontrar el primer token de tipo `Identifier` que encontnró el parser y extraer su valor, como se ve en el siguiente ejemplo:


```python
for token in statement:
    if isinstance(token, sqlparse.sql.Identifier):
        print(token.get_name().upper())
        break
```

    MY_TABLE


## Extrayendo una lista de tablas y sus nombres

El volcado SQL puede tener una mezcla de definiciones de estructuras de datos y otros tipos de código SQL, por ejemplo un query de búsqueda

```sql
CREATE TABLE IF NOT EXISTS MY_TABLE (ID TLLAVE NOT NULL,
    CONSTRAINT PK_MY_TABLE PRIMARY KEY (ID));

SELECT * FROM ANOTHER_TABLE;

CREATE TABLE IF NOT EXISTS MY_OTHER_TABLE (ID TLLAVE NOT NULL,
    CONSTRAINT PK_MY_TABLE PRIMARY KEY (ID));
```

lo que hacemos es utilizar `sqlparse` para encontrar cada statement y determiar si es de tipo `CREATE` de modo que para statements de este tipo aplicamos el algoritmo de la sección anterior para encontrar el nombre de la tabla.


```python
SQLDUMP = """CREATE TABLE IF NOT EXISTS MY_TABLE (ID TLLAVE NOT NULL,
    CONSTRAINT PK_MY_TABLE PRIMARY KEY (ID));

SELECT * FROM ANOTHER_TABLE;

CREATE TABLE IF NOT EXISTS MY_OTHER_TABLE (ID TLLAVE NOT NULL,
    CONSTRAINT PK_MY_TABLE PRIMARY KEY (ID));
"""

parsed = sqlparse.parse(SQLDUMP)
for i, statement in enumerate(parsed):
    print(f"{i}. {statement.get_type()}")
```

    0. CREATE
    1. SELECT
    2. CREATE



```python
def get_name(statement: Statement) -> Optional[str]:
    for token in statement:
        if isinstance(token, sqlparse.sql.Identifier):
            return token.value
    return None 
```


```python
for i, statement in enumerate(parsed):
    statement_type = statement.get_type()
    if statement_type == "CREATE":
        name = get_name(statement)
        print(f"{i}. {statement_type}: {name}")
```

    0. CREATE: MY_TABLE
    2. CREATE: MY_OTHER_TABLE


### Determinando el tipo de objeto creado


En un caso más general, podemos tener volcados sql con varios tipos de objetos, por ejemplo

```sql
CREATE TABLE MY_TABLE (ID INTEGER NOT NULL);

CREATE INDEX MY_INDEX ON MY_TABLE(ID);
```

analizando los tokens de cada statement es posible determinar el tipo de objeto.


```python
SQL = """CREATE TABLE MY_TABLE (ID INTEGER NOT NULL);

SELECT * FROM MY_OTHER_TABLE;

CREATE INDEX MY_INDEX ON MY_TABLE(ID);
"""

parsed = sqlparse.parse(SQL)
statement = parsed[0]


```


```python
type_found = False 
name_found = False 
for token in statement:
    if type_found and name_found:
        break
    elif token.ttype is Keyword and not type_found:
        type_found = True 
        token_type = token.value
    elif isinstance(token, sqlparse.sql.Identifier) and not name_found:
        name_found = True 
        token_name = token.value
print (f"tipo: {token_type}, nombre: {token_name}")
```

    tipo: TABLE, nombre: MY_TABLE


En el código anterior asumimos que todas las cláusulas son simples, es decir del estilo "CREATE ....", si estuvieran agrupadas, por ejemplo "(CREATE ....)" el  algoritmo ya no es tan simple, pues debe de realizar el escaneo de manera recursiva, un ejemplo de este tipo de algoritmo se encuentra en el repositorio de `sqlparse`:

[https://github.com/andialbrecht/sqlparse/blob/master/examples/extract_table_names.py](https://github.com/andialbrecht/sqlparse/blob/master/examples/extract_table_names.py)

### Extrayendo el nombre y tipo de objeto creado de un volcado completo


```python
SQL = """CREATE TABLE MY_TABLE (ID INTEGER NOT NULL);

SELECT * FROM MY_OTHER_TABLE;

CREATE INDEX MY_INDEX ON MY_TABLE(ID);
"""

@dataclass
class Metadata:
    type: str
    name: str 
    
def get_metadata(statement: Statement) -> Metadata:
    type_found = False 
    name_found = False 
    object_name = None 
    object_type = None 
    for token in statement:
        if type_found and name_found:
            break
        elif token.ttype is Keyword and not type_found:
            type_found = True 
            object_type = token.value
        elif isinstance(token, sqlparse.sql.Identifier) and not name_found:
            name_found = True 
            object_name = token.value
    return Metadata(name=object_name, type=object_type)


parsed = sqlparse.parse(SQL)

for i, statement in enumerate(parsed):
    name_found = False 
    if statement.get_type() != "CREATE":
        continue
    metadata = get_metadata(statement)
    print(i, metadata)
```

    0 Metadata(type='TABLE', name='MY_TABLE')
    2 Metadata(type='INDEX', name='MY_INDEX')


## Referencias

1. [https://sqlparse.readthedocs.io/en/latest/](https://sqlparse.readthedocs.io/en/latest/)
2. [https://github.com/andialbrecht/sqlparse/blob/master/examples/extract_table_names.py](https://github.com/andialbrecht/sqlparse/blob/master/examples/extract_table_names.py)

