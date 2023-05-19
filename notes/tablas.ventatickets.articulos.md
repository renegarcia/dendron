---
id: fgs2caedois1c3sk99b9uok
title: Articulos
desc: ''
updated: 1684305209349
created: 1684280098125
---
```sql
# SQL> show table ventatickets_articulos;
ID                              (TLLAVE) INTEGER Not Null 
TICKET_ID                       (TLLAVE) INTEGER Not Null 
PRODUCTO_CODIGO                 (TCODIGOPRODUCTO) VARCHAR(20) Not Null 
PRODUCTO_NOMBRE                 (TCADENALARGA) VARCHAR(255) Not Null 
CANTIDAD                        (TCANTIDAD) FLOAT Not Null 
GANANCIA                        (TMONEDA) NUMERIC(18, 4) Nullable 
DEPARTAMENTO_ID                 (TLLAVE) INTEGER Nullable 
PAGADO_EN                       (TFECHAHORA) TIMESTAMP Nullable 
USA_MAYOREO                     (TBOOLEANO) CHAR(1) Nullable DEFAULT 'f'
PORCENTAJE_DESCUENTO            (TCANTIDAD) FLOAT Nullable 
IMPUESTOS_USADOS                (TCADENALARGA) VARCHAR(255) Nullable 
IMPUESTO_UNITARIO               (TMONEDA) NUMERIC(18, 4) Nullable 
PRECIO_USADO                    (TMONEDA) NUMERIC(18, 4) Nullable 
CANTIDAD_DEVUELTA               (TCANTIDAD) FLOAT Not Null DEFAULT 0
FUE_DEVUELTO                    (TBOOLEANO) CHAR(1) Not Null DEFAULT 'f'
PORCENTAJE_PAGADO               (TMONEDA_4_DECIMALES) INTEGER Nullable DEFAULT 0
PRECIO_FINAL                    (TMONEDA) NUMERIC(18, 4) Nullable DEFAULT 0
AGREGADO_EN                     (TFECHAHORA) TIMESTAMP Nullable 
TOTAL_ARTICULO                  (TMONEDA) NUMERIC(18, 4) Nullable DEFAULT NULL
CONSTRAINT PK_VENTATICKETS_ARTICULOS:
  Primary key (ID)

Triggers on Table VENTATICKETS_ARTICULOS:
VENTATICKETS_ARTICULOS_BI, Sequence: 0, Type: BEFORE INSERT, Active
```