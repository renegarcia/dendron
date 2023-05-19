---
id: scfbibm6ikvk5ydyk3uc7ap
title: Relaciones
desc: ''
updated: 1684307000924
created: 1684305308903
---

```mermaid
classDiagram
    Clientesv2 <.. Facturacion
    Ventatickets <.. Articulo
    Caja <.. Ventatickets
    Usuario <.. Ventatickets
    Clientev2 <.. Ventatickets
    Factura <.. Ventatickets
    Turno <.. Ventatickets
    Caja <.. Turno
    Usuario <.. Turno
    Operacion <.. Turno
    class Usuario
    class Turno
```