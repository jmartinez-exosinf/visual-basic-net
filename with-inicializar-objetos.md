# 💡 Tip VB.NET: Usa `With` para inicializar objetos de forma limpia

En VB.NET, puedes usar la instrucción `With` para inicializar un objeto y asignar múltiples propiedades de forma compacta y legible.

---

## ✅ Ejemplo:

```vbnet
Dim persona As New Persona With {
    .Nombre = "Jose",
    .Edad = 30,
    .Ciudad = "Monterrey"
}
```

🧠 Ventajas:

Reduce líneas de código.
Mejora la legibilidad.
Ideal para inicializar objetos en listas o estructuras complejas.


📌 Recomendación:
Usa With cuando necesites crear objetos con varias propiedades, especialmente si estás agregándolos a colecciones como List(Of T).
