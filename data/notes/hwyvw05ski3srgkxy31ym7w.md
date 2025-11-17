
## Methods to Convert XML to JSON

```python
import xmltodict
import json
import os

# Directorio con tus archivos XML
directorio = 'ruta/a/tus/facturas'

# Procesar cada archivo XML
for archivo in os.listdir(directorio):
    if archivo.endswith('.xml'):
        with open(os.path.join(directorio, archivo), 'r') as xml_file:
            xml_content = xml_file.read()
            datos_json = xmltodict.parse(xml_content)
            
            # Guardar como archivo JSON
            with open(archivo.replace('.xml', '.json'), 'w') as json_file:
                json.dump(datos_json, json_file, indent=4)

```
