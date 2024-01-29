//PARA QUE LA COLUMNA PASE A FILAS SEPARADAS POR "," EN UNA AGRUPACION "COLUMNA A AGRUPAR"

Table.Gruop(
  #"paso anterior", {"Columna a agrupar"},
  {{"columna a filas", each Text.Combine(List.Distinct(_[columna a filas]), ", ")}})

//PARA HALLAR EL AÑO CON EL MAXIMO DE VENTAS AGRUPADOS POR "COLUMNA A AGRUPAR"

Table.Gruop(
  #"paso anterior", {"Columna a agrupar"},
  
  {
    {"columna a filas", each Text.Combine(List.Distinct(_[columna a filas]), ", ")}
    {"MaxVentasYear", each Table.Max(_, "Ventas")[Year]}  
    
  })
