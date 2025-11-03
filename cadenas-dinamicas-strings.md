# 🧵 Construcción de cadenas dinámicas en VB.NET
En Visual Basic .NET, construir cadenas dinámicas (strings) es una tarea común. Hay varias formas de hacerlo, pero dos de las más recomendadas son:
- ```String.Format```
- Interpolación de cadenas ```($"")```

# 🔧 1. Usando ```String.Format```
Este método permite insertar valores en una cadena utilizando marcadores de posición ```{0}```, ```{1}```, etc.

## 🧪 Ejemplo:
```VisualBasic
Dim nombre As String = "Jose"
Dim edad As Integer = 30
Dim mensaje As String = String.Format("Hola {0}, tienes {1} años.", nombre, edad)
Console.WriteLine(mensaje)
```

Salida:
```VisualBasic
Hola Jose, tienes 30 años.
```

# 🔧 2. Usando interpolación de cadenas ```($"")```
Desde VB.NET 14 (Visual Studio 2015), puedes usar interpolación de cadenas para una sintaxis más limpia y legible.

## 🧪 Ejemplo:
```VisualBasic
Dim nombre As String = "Jose"
Dim edad As Integer = 30
Dim mensaje As String = $"Hola {nombre}, tienes {edad} años."
Console.WriteLine(mensaje)
```

Salida:
```
Hola Jose, tienes 30 años.
```

# ✅ ¿Cuál usar?
- ```String.Format```: Compatible con versiones antiguas. Menos legible.
- Interpolación ```$""```. Más limpio y fácil de leer. Requiere VB.NET 14 o superior.

# 🧩 Tip adicional
Puedes combinar estos métodos con formatos específicos, por ejemplo:
```VisualBasic
Dim total As Decimal = 1234.56D
Dim mensaje As String = String.Format("Total: {0:C}", total)
Console.WriteLine(mensaje) ' Salida: "Total: $1,234.56" (según configuración regional)
```

O con interpolación:
```VisualBasic
Dim total As Decimal = 1234.56D
Dim mensaje As String = $"Total: {total:C}"
Console.WriteLine(mensaje)
```
