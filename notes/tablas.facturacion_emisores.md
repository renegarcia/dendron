---
id: qi6wbryy5wckdo7m70ouv6b
title: Facturacion_emisores
desc: ''
updated: 1684305134946
created: 1684302081229
---


```sql
# SQL> show table FACTURACION_EMISORES;

    ID                              (TLLAVE) INTEGER Not Null 
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
    ACTIVO                          (TBOOLEANO) CHAR(1) Nullable 
    REGIMENES                       (TNOTA) BLOB segment 80, subtype BINARY Nullable 
    CONSTRAINT PK_FACTURACION_EMISORES:
      Primary key (ID)

    Triggers on Table FACTURACION_EMISORES:
    FACTURACION_EMISORES_BI, Sequence: 0, Type: BEFORE INSERT, Active
```