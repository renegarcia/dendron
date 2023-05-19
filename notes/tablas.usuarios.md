---
id: sdht8svbqr805yg33v34nbh
title: Usuarios
desc: ''
updated: 1684305194014
created: 1684279621924
---


```sql
# SQL> show table usuarios;

ID                              (TLLAVE) INTEGER Not Null 
NOMBRE_COMPLETO                 (TCADENALARGA) VARCHAR(255) Nullable 
DIRECCION                       (TCADENALARGA) VARCHAR(255) Nullable 
TELEFONO                        (TCADENAMEDIANA) VARCHAR(50) Nullable 
USUARIO                         (TCADENAMEDIANA) VARCHAR(50) Not Null 
CLAVE                           (TCADENAMEDIANA) VARCHAR(50) Not Null 
PERMISOS                        (TPERMISOS) BLOB segment 80, subtype BINARY Nullable 
CREATED_ON                      (TFECHAHORA) TIMESTAMP Nullable 
CORREO                          (TCADENALARGA) VARCHAR(255) Nullable 
ESTA_EN_CAJA_ID                 (TLLAVE) INTEGER Nullable 
ELIMINADO_EN                    (TFECHAHORA) TIMESTAMP Nullable 
CONSTRAINT PK_USUARIOS:
  Primary key (ID)

Triggers on Table USUARIOS:
USUARIOS_BI, Sequence: 0, Type: BEFORE INSERT, Active
```

