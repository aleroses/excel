# Excel intermedio

## Sesión 01: Formato Personalizado

Objetivos:
- Formato Personalizado
- Formato Condicional

### Formato Personalizado

El Formato Personalizado en Excel es una herramienta que te permite definir cómo se muestran los valores en una celda sin alterar el contenido real de la misma, permitiendo crear formatos únicos para números, fechas y texto para mejorar la visualización de datos. Se accede presionando Ctrl+1 (o haciendo clic derecho y seleccionando "Formato de celdas") y eligiendo la pestaña "Número" y luego "Personalizada". 

Cómo funciona:

1. **Categoría Personalizada**: 
    
    Dentro de la sección "Personalizada", puedes escribir un código que defina el formato deseado. 
    
2. **Sintaxis de Códigos**: 
    
    Se utilizan códigos específicos para definir cómo se mostrarán los datos.
    
    - **Números**: Los símbolos `#` (almohadilla) y `0` (cero) se usan para mostrar dígitos. El `#` es opcional para los dígitos, mientras que el `0` es obligatorio. 
    - **Fechas**: Las letras `d` (día), `m` (mes), y `a` (año) se usan para definir formatos de fecha. 
    - **Texto**: Puedes incluir texto entre comillas o usar el asterisco `*` para llenar con un carácter. 

![Custom](https://i.postimg.cc/PrLWwGQ6/1-1-custom.png)

3. **Secciones para diferentes valores**: 
    
    Puedes definir formatos distintos para números positivos, negativos, ceros y texto, separados por punto y coma (`;`). 
    
    - `[FormatoPositivo];[FormatoNegativo];[FormatoCero];[FormatoTexto]`. 
    
4. **Aplicar el formato**: 
    
    Selecciona las celdas, presiona Ctrl+1, elige "Personalizada", escribe el código y haz clic en "Aceptar". 
    

> Nota: Estos códigos **no cambian el valor real de la celda**, solo **cómo se muestra**.

```bash
0
0.00
#,##0
#,##0.00
#,##0_);(#,##0)
#,##0_);[Red](#,##0)
#,##0.00_);(#,##0.00)
#,##0.00_);[Red](#,##0.00)
$#,##0_);($#,##0)
$#,##0_);[Red]($#,##0)
$#,##0.00_);($#,##0.00)
$#,##0.00_);[Red]($#,##0.00)
0%
0.00%
0.00E+00
##0.0E+0
# ?/?
# ??/??
m/d/yyyy
d-mmm-yy
d-mmm
mmm-yy
h:mm AM/PM
h:mm:ss AM/PM
h:mm
h:mm:ss
m/d/yyyy h:mm
mm:ss
mm:ss.0
@
[h]:mm:ss
_($* #,##0_);_($* (#,##0);_($* "-"_);_(@_)
_(* #,##0_);_(* (#,##0);_(* "-"_);_(@_)
_($* #,##0.00_);_($* (#,##0.00);_($* "-"??_);_(@_)
_(* #,##0.00_);_(* (#,##0.00);_(* "-"??_);_(@_)
_-[$S/.-es-PE] * #,##0.00_ ;_-[$S/.-es-PE] * -#,##0.00 ;_-[$S/.-es-PE] * "-"??_ ;_-@_ 
```

La estructura general de un formato personalizado en Excel es:

```
[Positivo];[Negativo];[Cero];[Texto]
```

- Si defines 1 sección → aplica a todo.
    
- Si defines 2 secciones → la primera es para positivos y ceros, la segunda para negativos.
    
- Si defines 3 → positivo, negativo, cero.
    
- Si defines 4 → positivo, negativo, cero, texto.
    

#### Formatos numéricos básicos

- **0** → Muestra siempre al menos un dígito.  
    Ej: 5 → `5`; 0.5 → `1` (redondea).
    
- **0.00** → Siempre muestra 2 decimales.  
    Ej: 5 → `5.00`; 3.1 → `3.10`.
    
- **#,##0** → Usa separador de miles, sin decimales.  
    Ej: 12345 → `12,345`.
    
- **#,##0.00** → Igual que el anterior pero con 2 decimales.  
    Ej: 12345.6 → `12,345.60`.
    

#### Formatos con positivos y negativos

- **#,##0_);(#,##0)**  
    Positivos normales, negativos entre paréntesis.  
    Ej: 1234 → `1,234 `; -1234 → `(1,234)`.
    
- **`#,##0_);[Red](#,##0)`**  
    Igual que el anterior, pero los negativos en **rojo**.
    
- **#,##0.00_);(#,##0.00)**  
    Igual, pero con 2 decimales.
    
- **#,##0.00_);[Red](https://chatgpt.com/g/g-p-68d8b7a690d48191800d1a9e7d2d5d1f-excel/c/68dec77a-7f04-8331-a714-22b9f19e03ab#,##0.00)**  
    Negativos en rojo, con 2 decimales.
    

---

### 💲 **Formatos monetarios (con $)**

- **$#,##0_);($#,##0)**  
    Positivos con `$`, negativos entre paréntesis con `$`.
    
- **$#,##0_);[Red](https://chatgpt.com/g/g-p-68d8b7a690d48191800d1a9e7d2d5d1f-excel/c/$#,##0)**  
    Igual, pero negativos en rojo.
    
- **$#,##0.00_);($#,##0.00)**  
    Con 2 decimales.
    
- **$#,##0.00_);[Red](https://chatgpt.com/g/g-p-68d8b7a690d48191800d1a9e7d2d5d1f-excel/c/$#,##0.00)**  
    Con 2 decimales y negativos en rojo.
    

---

### 📊 **Porcentajes y notación científica**

- **0%** → Muestra el número como porcentaje sin decimales.  
    Ej: 0.25 → `25%`.
    
- **0.00%** → Igual, pero con 2 decimales.  
    Ej: 0.256 → `25.60%`.
    
- **0.00E+00** → Notación científica con 2 decimales.  
    Ej: 123456 → `1.23E+05`.
    
- **##0.0E+0** → Notación científica con 1 decimal.
    

---

### ➗ **Fracciones**

- **# ?/?** → Muestra como fracción simple.  
    Ej: 0.5 → `1/2`; 2.25 → `2 1/4`.
    
- **# ??/??** → Muestra fracciones con hasta 2 dígitos en numerador y denominador.  
    Ej: 2.125 → `2 1/8`.
    

---

### 📅 **Fechas**

- **m/d/yyyy** → 3/14/2025.
    
- **d-mmm-yy** → 14-Mar-25.
    
- **d-mmm** → 14-Mar.
    
- **mmm-yy** → Mar-25.
    

---

### ⏰ **Horas**

- **h:mm AM/PM** → 1:30 PM.
    
- **h:mm:ss AM/PM** → 1:30:45 PM.
    
- **h:mm** → 13:30.
    
- **h:mm:ss** → 13:30:45.
    
- **m/d/yyyy h:mm** → 3/14/2025 13:30.
    
- **mm:ss** → 05:30 (minutos y segundos).
    
- **mm:ss.0** → 05:30.5 (con décimas).
    
- **@** → Para texto (lo que escribas se muestra tal cual).
    
- **[h]:mm:ss** → Suma horas totales sin reiniciar en 24h. Ej: 27:45:00.
    

---

### 💵 **Formatos más complejos (alineación y símbolos)**

Estos usan `_` (espacio), `*` (relleno), y localización:

- ___($_ #,##0_);_($_ (#,##0);_($* "-"_);_(@_)**  
    → Positivos con $, negativos entre paréntesis, ceros como "-", y texto alineado.
    
- ___(_ #,##0_);_(_ (#,##0);_(* "-"_);_(@_)**  
    → Igual pero sin símbolo $.
    
- ___($_ #,##0.00_);_($_ (#,##0.00);_($* "-"??_);_(@_)**  
    → Como los anteriores pero con 2 decimales.
    
- **_-[$S/.-es-PE] * #,##0.00_ ;...**  
    → Lo mismo, pero con **símbolo de moneda en Soles (S/.)** y localización española (Perú).
    

---

👉 En resumen:

- `0` fuerza dígitos.
    
- `#` muestra dígitos solo si existen.
    
- `,` separa miles.
    
- `.` define decimales.
    
- `()` indica negativos entre paréntesis.
    
- `[Red]` cambia color.
    
- `$` muestra moneda.
    
- `@` representa texto.
    
- `_` agrega espacio para alinear.
    
- `*` repite el carácter para rellenar.
    
- `[h]` hace que las horas se acumulen.
    

---

¿Quieres que te arme una **tabla práctica** con ejemplos (valor → cómo se vería con cada formato) para que lo veas más claro en la práctica?



## Colors

`#090b10`
`#0f111a`
`#4f46e5`

`alt 126 ~`