# 🚀 Uso de Async y Await en Controllers VB.NET
En aplicaciones ASP.NET MVC o Web API, los controladores pueden beneficiarse del uso de **métodos asíncronos** para mejorar la escalabilidad y el rendimiento, especialmente cuando se realizan operaciones I/O como consultas a base de datos o llamadas a servicios externos.

## ✅ ¿Por qué usar Async y Await?
- **Mejor rendimiento**: libera el hilo mientras espera la respuesta.
- **Escalabilidad**: permite atender más solicitudes concurrentes.
- **Código más limpio**: evita bloqueos y callbacks complejos.


## 🧪 Ejemplo básico en un Controller
```VisualBasic
Imports System.Threading.Tasks
Imports Microsoft.AspNetCore.Mvc
Imports Npgsql

Public Class ConfiguracionController
    Inherits Controller

    <HttpGet>
    Public Async Function ObtenerConfiguracion() As Task(Of IActionResult)
        Dim resultado As New DataTable()
        Using conn As New NpgsqlConnection("Host=localhost;Database=test;Username=postgres;Password=1234")
            Await conn.OpenAsync()
            Using cmd As New NpgsqlCommand("SELECT * FROM ""configdistributiondetalles"" LIMIT 10;", conn)
                Using reader As NpgsqlDataReader = Await cmd.ExecuteReaderAsync()
                    resultado.Load(reader)
                End Using
            End Using
        End Using
        Return Ok(resultado)
    End FunctionEnd ClassMostrar más líneas
```

## 🔍 ¿Qué hace este código?
- Marca el método como asíncrono:
```VisualBasic
Public Async Function ObtenerConfiguracion() As Task(Of IActionResult)
```

- Usa **Await** en operaciones que tardan (abrir conexión, ejecutar consulta).
-- Devuelve un **Task(Of IActionResult)** para integrarse con el pipeline de ASP.NET.

## ✅ Buenas prácticas
- Usa Async solo en operaciones I/O (no en cálculos simples).
- Evita bloquear con `.Result` o `.Wait()`.
- Propaga Async hasta el nivel más alto (controlador → servicio → repositorio).
