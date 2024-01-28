//PARA CALCULAR LA SUMA ACUMULADA POR MES-AÑO Y MARCA
//EN CASO DE CONTAR FILAS, REEMPLAZAR EL SUMX POR COUNTROWS

VAR mes_actual = FORMAT(Sales[Date], "mmm-yy")
VAR marca_actual = RELATED(Products[Band])

RETURN
  SUMX(
      FILTER(
        Sales,
        FORMAT(Sales[Date], "mmm-yy") = mes_actual &&
        RELATED(Products[Band]) = marca_actual
      )
      Sales[Units]
  )
