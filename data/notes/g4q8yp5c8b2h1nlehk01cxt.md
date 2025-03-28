
Simple program that reads an url and prints the last part of the path as a title. 

<script src="https://gist.github.com/renegarcia/9e80f1c84c57753b5aa4e19f0b8198db.js"></script>

# Code 

```python
from urllib.parse import urlparse

def get_last_path(url:str) -> str:
    # Parse the URL
    parsed_url = urlparse(url)

    # Get the path from the parsed URL
    path = parsed_url.path

    # Split the path by slashes and get the last part
    path_parts = path.split('/')
    last_part = path_parts[-1]

    return last_part

def path_to_title(path:str) -> str:
    return path.replace("-", " ").title()

def main():
    url = input("Enter the URL: ")
    path = get_last_path(url)
    title = path_to_title(path)
    print(title)

if __name__ == "__main__":
    while True:
        try:
            main()
        except KeyboardInterrupt:
            break
```

# Case of use

I use this to format references in my mardown documents. For example, given the url 

``` 
https://stackoverflow.com/questions/76392847/flutter-firebase-to-python-firebase
```

The program outputs

```
Flutter Firebas To Python Firebase
```

which I use to link to the question, like so:

```markdown
[Flutter Firebas To Python Firebase](https://stackoverflow.com/questions/76392847/flutter-firebase-to-python-firebase)
```

# References

* [Gist version](https://gist.github.com/renegarcia/9e80f1c84c57753b5aa4e19f0b8198db)
* [Interactive version in a jupyter notebook](https://colab.research.google.com/drive/1MhXnLZnS7I_oaRjYExcg63TND32YDcHL?usp=sharing)