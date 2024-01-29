//Total de ventas DEL DIA con más ventas (Cuando la tabla es ua dimensión)
//tener cuidado con la transición de contexto (valor que filtra una columna)

MAXX(
  'Calendar',
  [TotalVentas]
)

//Total de ventas DEL PRODUCTO con más ventas (Cuando la tabla es ua dimensión)
//tener cuidado con la transición de contexto (valor que filtra una columna)

MAXX(
  Products,
  [TotalVentas]
)


//Total de Ventas DE LA REGION con más ventas (Region es parte de la tabla de hechos de ventas)
MAXX(
  VALUES(Sales[Region]),
  [TotalVentas]
)

//PRODUCTO MAS VENDIDO (Referencia: Total de ventas DEL PRODUCTO con más ventas)

IF(
  [TotalVentas] <> Blank(),
  CONCATENEX(
    TOPN(
      1,
      Products,
      [TotalVentas]
    ),
    Products[Product],
    UNICHAT(10)
  )
)
