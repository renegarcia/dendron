

# Create named temporary file

```python
import tempfile

def create_temp_file(prefix):
    temp_file = tempfile.NamedTemporaryFile(prefix=prefix, delete=False)
    temp_file.close()
    return temp_file.name

# Example usage
prefix = "my_prefix"
temp_file_path = create_temp_file(prefix)
print("Temporary file created:", temp_file_path)
```

From the above code, note that the file path can be retrived with `temp_file.name`.

## Access the file directory


```python
from pathlib import Path 

temp_file = create_temp_file("my_prefix")
path = Path(temp_file)
print(path.parent)
```


# References

1. [Source](https://chat.openai.com/share/abe75dba-545e-4e17-83db-b59d60ed8c98)