Obtener la fila anterior en Power Query

let
Datelist = List.Transform({null} & Table.RemoveLastN([All], 1)[Date], each Date.AddDays(_, -1)),
AllLists = Table.ToColumns([All]),
ColHeaders = Table.ColumnNames([All]) & {"EndDate"},
ConcatList = AllLists & {Datelist}

in
Table.FromColumns(ConcatList, ColHeaders)
![image](https://github.com/Rockolonso/RockoBI/assets/157999829/998ba88e-32ba-41df-a1a7-17d417c86c30)


