---
id: gjj6h9m1to6x9bauals934g
title: Facturacion
desc: ''
updated: 1684305105919
created: 1684302319852
---


```sql
# SQL> show table clientesv2_facturacion;
    CLIENTESV2_ID                   (TLLAVE) INTEGER Not Null 
    RFC                             (TRFC) VARCHAR(13) Not Null 
    NOMBRE                          (TCADENALARGA) VARCHAR(255) Nullable 
    CALLE                           (TCADENALARGA) VARCHAR(255) Nullable 
    NOEXTERIOR                      (TCADENAMEDIANA) VARCHAR(50) Nullable 
    NOINTERIOR                      (TCADENAMEDIANA) VARCHAR(50) Nullable 
    COLONIA                         (TCADENALARGA) VARCHAR(255) Nullable 
    LOCALIDAD                       (TCADENALARGA) VARCHAR(255) Nullable 
    MUNICIPIO                       (TCADENALARGA) VARCHAR(255) Nullable 
    ESTADO                          (TCADENAMEDIANA) VARCHAR(50) Nullable 
    PAIS                            (TCADENALARGA) VARCHAR(255) Nullable 
    EMAIL                           (TCADENALARGA) VARCHAR(255) Nullable 
    REFERENCIA                      (TCADENALARGA) VARCHAR(255) Nullable 
    CODIGOPOSTAL                    (TCODIGOPOSTAL) INTEGER Nullable 
    REGIMENES                       (TNOTA) BLOB segment 80, subtype BINARY Nullable 
    ELIMINADO_EN                    (TFECHAHORA) TIMESTAMP Nullable 
    REGIMEN_FISCAL                  (TCADENAMEDIANA) VARCHAR(50) Nullable 
    CONSTRAINT PK_CLIENTESV2_FACTURACION_ID:
      Primary key (CLIENTESV2_ID)
```