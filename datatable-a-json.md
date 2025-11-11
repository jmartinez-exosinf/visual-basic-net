# 🗞️ Convertir un DataTable a JSON en VB.NET

En VB.NET, puedes convertir un objeto `DataTable` a una cadena JSON utilizando la biblioteca **Json.NET** (`Newtonsoft.Json`). Esto es útil para exportar datos, integrarte con APIs o guardar información estructurada.

---

## ✅ Requisitos

1. Asegúrate de tener instalada la biblioteca **Newtonsoft.Json**.
   - Puedes instalarla desde NuGet:
     ```
     Install-Package Newtonsoft.Json
     ```

---

## ✅ Ejemplo de código

```vbnet
Imports Newtonsoft.Json
Imports System.Data

' Crear un DataTable de ejemplo
Dim dataTable As New DataTable()
dataTable.Columns.Add("ID")
dataTable.Columns.Add("Nombre")

dataTable.Rows.Add("1", "Jose")
dataTable.Rows.Add("2", "Nestor")

' Convertir a JSON
Dim json As String = JsonConvert.SerializeObject(dataTable)

' Mostrar el resultado
Console.WriteLine(json)
```

## 🧠 Explicación
- `JsonConvert.SerializeObject(dataTable)` convierte el `DataTable` en una cadena **JSON**.
- Cada fila del `DataTable` se convierte en un objeto **JSON** con las columnas como claves.
- El resultado es un arreglo de objetos **JSON**.


## 📌 Resultado esperado
```json
[  {    "ID": "1",    "Nombre": "Jose"  },  {    "ID": "2",    "Nombre": "Nestor"  }]
```

## 🧪 Tip adicional
Si necesitas convertir solo una fila o un conjunto filtrado, puedes usar **LINQ** para seleccionar los datos antes de serializar.
