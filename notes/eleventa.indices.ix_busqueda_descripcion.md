---
id: 2qjmpthybalr6dv6vjzqsfg
title: IX_BUSQUEDA_DESCRIPCION
desc: null
updated: 1684521573
created: 1684521573
---


```sql
 CREATE INDEX IX_BUSQUEDA_DESCRIPCION ON PRODUCTOS COMPUTED BY (UPPER (descripcion));
```
