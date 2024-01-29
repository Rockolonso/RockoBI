//PARA APERTURAR FECHAS EN FILAS ENTRE 2 FECHAS

List.Dates(
  [Fecha de Inicio],
  Duration.Days([Fecha de Cese]-[Fecha de Inicio]) +1,
  #duration (1,0,0,0)
)
