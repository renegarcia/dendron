
### Resultado

<script src="https://gist.github.com/renegarcia/2ba8eebc987ee99c2c4ce5ff2ee75081.js"></script>


### Detalles

Necesitamos utilizar los paquetes `string` y `secrets`.

```python
from secrets import choice
import string
```

A continuación definimos el alfabeto y la función generadora.

```python
ALPHABET = string.ascii_letters + string.digits + string.punctuation

def password_generator(len:int =10, alphabet: list[str] = ALPHABET) -> str:
    return "".join(choice(alphabet) for i in range(len))
```





### Referencias

1. https://docs.python.org/3/library/secrets.html

2. https://gist.github.com/renegarcia/2ba8eebc987ee99c2c4ce5ff2ee75081

