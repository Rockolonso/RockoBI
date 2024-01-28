//UNIDADES REEMBOLSADAS por Mes de Reembolso

CALCULATE ( 
          SUM(Reembolsos[UnidadesReemb]) ,
          USERELATIONSHIP ('Calendar'[Date]. Reembolsos[FechaReemb])
)

//UNIDADES REEMBOLSADAS por Mes de Venta

SUM(Reembolsos[UnidadesReemb])
