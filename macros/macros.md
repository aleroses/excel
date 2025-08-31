# Automatizar tareas

Secuencia de instrucciones en VBA.

- REC: Grabadora de Macros
- Editor VB for Applications

```bash
Application.Workbooks
Application.Worksheets
Application.Charts
Application.Range
```

## 🛠 PASO 1: Habilitar la pestaña "Desarrollador"

Si no ves la pestaña **"Desarrollador"** (Developer) en la cinta de opciones:

1. Haz clic en **Archivo** → **Opciones**.
    
2. Ve a **Personalizar cinta de opciones**.
    
3. Marca la casilla **"Desarrollador/Programador"** y haz clic en **Aceptar**.
    

## 🛠 PASO 2: Abrir el editor de Visual Basic

1. En la pestaña **Programador**, haz clic en **Visual Basic**.
    
    - O usa el atajo: `Alt + F11`.
        
2. En el editor que se abre:
    
    - Ve al menú: **Insertar** → **Módulo**.
        
    - Esto crea un **nuevo módulo** (donde puedes escribir macros).
        

## 🧾 PASO 3: Pegar una macro

1. Pega el código en el módulo abierto.
    
2. Guarda el archivo como **Libro habilitado para macros** (`.xlsm`):
    
    - Archivo → Guardar como → Tipo: **Libro de Excel habilitado para macros (*.xlsm)**
        

📌 Nota: Si **guardar como** no te aparece, solo dale a Archivo → Guardar → No → Cambiar Libro de Excel `(*.xlsx)` por Libro de Excel habilitado para macros `(*.xlsm)` → Guardar

### ✅ 1. **Limpiar filas vacías**

**Objetivo**: Eliminar filas que están completamente vacías para mejorar la visualización y análisis.

```vba
Sub EliminarFilasVacias()
    Dim i As Long
    For i = Cells(Rows.Count, 1).End(xlUp).Row To 1 Step -1
        If Application.WorksheetFunction.CountA(Rows(i)) = 0 Then
            Rows(i).Delete
        End If
    Next i
End Sub
```

### ✅ 2. **Formato automático de tabla**

**Objetivo**: Aplicar formato a las tablas (bordes, negrita en encabezados, autoajuste de ancho de columnas).

```vba
Sub FormatearTabla()
    With Range("A1").CurrentRegion
        .Font.Name = "Calibri"
        .Font.Size = 11
        .Borders.LineStyle = xlContinuous
        .Rows(1).Font.Bold = True
        .Columns.AutoFit
    End With
End Sub
```

### ✅ 3. **Insertar fecha y hora actual**

**Objetivo**: Insertar una marca de tiempo al generar un nuevo reporte.

```vba
Sub InsertarFechaHora()
    Range("A1").Value = "Reporte generado el: " & Now
End Sub
```

### ✅ 4. **Guardar como PDF automáticamente**

**Objetivo**: Exportar la hoja como PDF con un nombre personalizado.

```vba
Sub ExportarComoPDF()
    Dim ruta As String
    ruta = ThisWorkbook.Path & "\Reporte_Costos_" & Format(Now, "yyyymmdd_hhmmss") & ".pdf"
    ActiveSheet.ExportAsFixedFormat Type:=xlTypePDF, Filename:=ruta
    MsgBox "Exportado como PDF en: " & ruta
End Sub
```

### ✅ 5. **Macro para duplicar hoja como plantilla**

**Objetivo**: Crear una copia de la hoja actual para comenzar un nuevo análisis.

```vba
Sub DuplicarHoja()
    Sheets("Hoja1").Copy After:=Sheets(Sheets.Count)
    ActiveSheet.Name = "Copia_" & Format(Now, "hhmmss")
End Sub
```

## 🛠 PASO 4: Ejecutar la macro

1. Cierra el editor (o presiona `Alt + Q`).
    
2. Regresa a Excel.
    
3. En la pestaña **Desarrollador**, haz clic en **Macros**.
    
4. Selecciona `EliminarFilasVacias` o cualquier otra macro añadida y haz clic en **Ejecutar**.
    

✅ ¡Listo!





