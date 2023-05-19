---
id: zx2eb90ilw3n77vv5zaw62h
title: Ventatickets
desc: ''
updated: 1684305201576
created: 1684280032134
---
```sql
# SQL> show table ventatickets;
ID                              (TLLAVE) INTEGER Not Null 
FOLIO                           (TFOLIO) INTEGER Nullable 
CAJA_ID                         (TLLAVE) INTEGER Nullable 
CAJERO_ID                       (TLLAVE) INTEGER Nullable 
NOMBRE                          (TCADENAMEDIANA) VARCHAR(50) Nullable 
CREADO_EN                       (TFECHAHORA) TIMESTAMP Nullable 
SUBTOTAL                        (TMONEDA) NUMERIC(18, 4) Nullable DEFAULT 0
IMPUESTOS                       (TMONEDA) NUMERIC(18, 4) Nullable DEFAULT 0
TOTAL                           (TMONEDA) NUMERIC(18, 4) Nullable DEFAULT 0
GANANCIA                        (TMONEDA) NUMERIC(18, 4) Nullable DEFAULT 0
ESTA_ABIERTO                    (TBOOLEANO) CHAR(1) Nullable DEFAULT 't'
CLIENTE_ID                      (TLLAVE) INTEGER Nullable 
VENDIDO_EN                      (TFECHAHORA) TIMESTAMP Nullable 
ES_MODIFICABLE                  (TBOOLEANO) CHAR(1) Nullable DEFAULT 't'
PAGO_CON                        (TMONEDA) NUMERIC(18, 4) Nullable 
MONEDA                          (TCODIGOMONEDA) VARCHAR(3) Nullable 
NUMERO_ARTICULOS                (TINTEGER) INTEGER Nullable DEFAULT 0
PAGADO_EN                       (TFECHAHORA) TIMESTAMP Nullable 
ESTA_CANCELADO                  (TBOOLEANO) CHAR(1) Nullable DEFAULT 'f'
OPERACION_ID                    (TLLAVE) INTEGER Nullable 
OLD_TICKET_ID                   (TLLAVE) INTEGER Nullable 
NOTAS                           (TNOTA) BLOB segment 80, subtype BINARY Nullable 
IMPRIMIR_NOTA                   (TBOOLEANO) CHAR(1) Nullable DEFAULT 't'
FORMA_PAGO                      (TFORMAPAGO) CHAR(10) Nullable 
REFERENCIA                      (TCADENALARGA) VARCHAR(255) Nullable 
FACTURA_ID                      (TLLAVE) INTEGER Nullable 
TOTAL_DEVUELTO                  (TMONEDA) NUMERIC(18, 4) Not Null DEFAULT 0
TOTAL_AHORRADO                  (TMONEDA) NUMERIC(18, 4) Not Null DEFAULT 0
TURNO_ID                        (TLLAVE) INTEGER Nullable 
TIPO_DE_CAMBIO                  (TMONEDA) NUMERIC(18, 4) Nullable DEFAULT 1
TOTAL_CREDITO                   (TMONEDA) NUMERIC(18, 4) Nullable DEFAULT 0
NOTAS_AL_PIE                    (TNOTA) BLOB segment 80, subtype BINARY Nullable DEFAULT NULL
REFRESCAR_TICKET                (TBOOLEANO) CHAR(1) Nullable DEFAULT 'F'
TOTAL_FACTURABLE                (TMONEDA) NUMERIC(18, 4) Not Null DEFAULT 0
CLIENTESV2_ID                   INTEGER Not Null DEFAULT 1
CLIENTESV2_CREDITO_ID           INTEGER Nullable 
ACTIVO                          CHAR(1) Nullable DEFAULT 't'
IMPRIMIR_DATOS_CLIENTE          CHAR(1) Nullable 
SALDO_CREDITO                   (TMONEDA) NUMERIC(18, 4) Not Null DEFAULT 0
IMPUESTOS_RETENIDOS             (TMONEDA) NUMERIC(18, 4) Not Null DEFAULT 0
CONSTRAINT PK_VENTATICKETS:
  Primary key (ID)

Triggers on Table VENTATICKETS:
VENTATICKETS_BI, Sequence: 0, Type: BEFORE INSERT, Active
```