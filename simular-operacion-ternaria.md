# Simular una Operación Ternaria en VB.NET con `If()` y `TryParse`

En VB.NET no existe directamente el operador ternario, sin embargo, puedes lograr el mismo comportamiento utilizando la función `If()` o una estructura `If...Then...Else`.

---

# ✅ Usando `If()` como operador ternario

La función `If()` en VB.NET puede actuar como un operador ternario. Su sintaxis es:
```vbnet
If(condición, valor_si_verdadero, valor_si_falso)
```

## Ejemplo con TryParse:
```vbnet
Dim PorcentajeSociedad As Decimal
PorcentajeSociedad = If(Decimal.TryParse(Valor, PorcentajeSociedad), PorcentajeSociedad, 0D)
```

## Explicación:

- ```Decimal.TryParse(...)``` intenta convertir el valor a Decimal.
- Si la conversión es exitosa (```True```), el valor convertido queda en ```PorcentajeSociedad```.
- Si falla (```False```), se asigna 0D como valor por defecto.

```vbnet
Dim PorcentajeSociedad As Decimal

If Not Decimal.TryParse(ExcelArray(row, 3).ToString(), PorcentajeSociedad) Then
    PorcentajeSociedad = 0D
End If
```

## 🧠 Recomendación
Usa ```If()``` cuando necesites una expresión compacta, y ```If...Then...Else``` cuando la lógica sea más compleja o requiera múltiples pasos.
