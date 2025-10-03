# Excel intermedio

[Curso Excel 2019 - Intermedio](https://youtu.be/rdRtDDV0-rg)

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

- `#,##0_);(#,##0)`  👈
    Positivos normales, negativos entre paréntesis.  
    Ej: 1234 → `1,234 `; -1234 → `(1,234)`.
    
- `#,##0_);[Red](#,##0)`  
    Igual que el anterior, pero los negativos en **rojo**.
    
- `#,##0.00_);(#,##0.00)`  👈
    Igual, pero con 2 decimales.
    
- `#,##0.00_);[Red](#,##0.00)`  
    Negativos en rojo, con 2 decimales.
    

#### Formatos monetarios (con $)

- `$#,##0_);($#,##0)`  👈
    Positivos con `$`, negativos entre paréntesis con `$`.
    
- `$#,##0_);[Red]($#,##0)`  
    Igual, pero negativos en rojo.
    
- `$#,##0.00_);($#,##0.00)`  👈
    Con 2 decimales.
    
- `$#,##0.00_);[Red]($#,##0.00)`  
    Con 2 decimales y negativos en rojo.
    

#### Porcentajes y notación científica

- **0%** → Muestra el número como porcentaje sin decimales.  
    Ej: 0.25 → `25%`.
    
- **0.00%** → Igual, pero con 2 decimales.  
    Ej: 0.256 → `25.60%`.
    
- **0.00E+00** → Notación científica con 2 decimales.  
    Ej: 123456 → `1.23E+05`.
    
- **##0.0E+0** → Notación científica con 1 decimal.
    

#### Fracciones

- **# ?/?** → Muestra como fracción simple.  
    Ej: 0.5 → `1/2`; 2.25 → `2 1/4`.
    
- **# ??/??** → Muestra fracciones con hasta 2 dígitos en numerador y denominador.  
    Ej: 2.125 → `2 1/8`.
    

#### Fechas

- **m/d/yyyy** → 3/14/2025.
    
- **d-mmm-yy** → 14-Mar-25.
    
- **d-mmm** → 14-Mar.
    
- **mmm-yy** → Mar-25.
    

#### Horas

- **h:mm AM/PM** → 1:30 PM.
    
- **h:mm:ss AM/PM** → 1:30:45 PM.
    
- **h:mm** → 13:30.
    
- **h:mm:ss** → 13:30:45.
    
- **m/d/yyyy h:mm** → 3/14/2025 13:30.
    
- **mm:ss** → 05:30 (minutos y segundos).
    
- **mm:ss.0** → 05:30.5 (con décimas).
    
- **@** → Para texto (lo que escribas se muestra tal cual).
    
- `[h]:mm:ss` → Suma horas totales sin reiniciar en 24h. Ej: 27:45:00.
    

#### Formatos más complejos (alineación y símbolos)

Estos usan `_` (espacio), `*` (relleno), y localización:

- `_($* #,##0_);_($* (#,##0);_($* "-"_);_(@_)`  
    → Positivos con $, negativos entre paréntesis, ceros como "-", y texto alineado.
    
- `_(* #,##0_);_(* (#,##0);_(* "-"_);_(@_)`*  
    → Igual pero sin símbolo $.
    
- `_($* #,##0.00_);_($* (#,##0.00);_($* "-"??_);_(@_)`  
    → Como los anteriores pero con 2 decimales.
    
- `_-[$S/.-es-PE] * #,##0.00_ ;_-[$S/.-es-PE] * -#,##0.00 ;_-[$S/.-es-PE] * "-"??_ ;_-@_ `
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
    

Otros

```
####.#
#.000
0.#
#.00
#.0#

???.???

# ???/???

#,##0.00
"S/."*   #,##0.00
"S/."* - #,##0.00
"S/."* . #,##0.00
"S/."** #,##0.00
```

#### 🔢 **Decimales opcionales**

- **####.#**
    
    - `#` = dígito si existe (no muestra ceros a la izquierda o al final).
        
    - Ejemplos:
        
        - `123.45` → `123.5`
            
        - `0.4` → `.4` (nota que no obliga al “0” antes del punto, si fuera 1.4 si aparece el 1).
            
- **#.000**
    
    - Siempre **3 decimales exactos**.
        
    - Ej: `12.3` → `12.300`
        
- **0.#**
    
    - El `0` obliga a que haya al menos un dígito antes del punto.
        
    - El `#` hace opcional el decimal.
        
    - Ej:
        
        - `5` → `5`
            
        - `5.2` → `5.2`
            
        - `5.23` → `5.2`
            
- **#.00**
    
    - Muestra como mínimo **2 decimales** si hay parte decimal, pero no muestra nada si no lo hay.
        
    - Ej:
        
        - `12.3` → `12.30`
            
        - `12` → `12`
            
- **#.0#**
    
    - Muestra al menos **1 decimal**, y el segundo decimal es opcional.
        
    - Ej:
        
        - `12.3` → `12.3`
            
        - `12.34` → `12.34`
            
        - `12` → `12.0`
            

#### 📐 **Alineación de decimales**

- **???.???**
    
    - `?` reserva espacio para dígitos (aunque no existan), lo que permite **alinear los decimales en columna**.
        
    - Ej:
        
        - `1.2` → `1.2  👈 2 espacios`
            
        - `123.45` → `123.45 👈 1 espacio`
            
        - `7` → `7.   👈 3 espacios`
            
    - Esto es muy usado en reportes contables para que todos los números queden bien alineados.
	    
	    ```
	     28.568|
	    256.52 |
	     14.7  |
	    ```

#### ➗ **Fracciones**

- **# ???/???**
    
    - Muestra número como fracción con hasta **3 dígitos en numerador y denominador**.
        
    - Ej:
        
        - `2.125` → `2 1/8`
            
        - `0.5` → `1/2`
	    
	    ```
	    2  1/8  |
	       1/2  |
	    ```

#### 💵 **Moneda y relleno con símbolo**

- `#,##0.00`
    
    - Ya lo vimos: separador de miles + 2 decimales.
        
- `"S/."* #,##0.00_*`
    
    - `"texto"` muestra literal lo que escribas (aquí `S/.`).
        
    - `*` repite el carácter siguiente para rellenar hasta el ancho de la celda.
        
    - En este caso, **rellena con espacios** (`" "`).
        
    - Ejemplo:
        
        - Si la celda es ancha → `S/. 1,234.50`
            
- `"S/."* - #,##0.00_*`
    
    - Rellena con **guiones** `-` hasta alinear.
        
    - Ej:
        
        - `S/.---- 1,234.50`
            
- `"S/."* . #,##0.00_*`
    
    - Rellena con **puntos** `.`.
        
    - Ej:
        
        - `S/..... 1,234.50`
            
- `"S/."** #,##0.00`
    
    - Doble `*` hace que el símbolo se repita de manera continua hasta rellenar.
        
    - Ej:
        
        - `S/.***** 1,234.50` (dependiendo del ancho de la celda).
            

---

👉 Resumen de las nuevas reglas que aparecieron aquí:

- `#` → muestra dígito si existe, pero no obliga.
    
- `0` → obliga a mostrar dígito, aunque sea 0.
    
- `?` → reserva espacio, útil para alinear.
    
- `"texto"` → escribe texto literal.
    
- `*` → rellena con el carácter que sigue.
    
- `**` → rellena repitiendo más intensamente el carácter.
    

#### Colores

En **Excel** los **formatos personalizados** permiten no solo controlar **cómo se ven los números**, sino también **el color** con el que se muestran (pero ojo: solo afecta la visualización, no el valor).

##### Colores disponibles en formatos personalizados

Excel tiene un conjunto limitado de colores predefinidos que se pueden usar directamente en los códigos de formato:

- **[Black]**
    
- **[Blue]**
    
- **[Cyan]**
    
- **[Green]**
    
- **[Magenta]**
    
- **[Red]**
    
- **[White]**
    
- **[Yellow]**
    

También puedes usar colores indexados por número, que corresponden a la paleta de Excel:

- **[Color1]** a **[Color56]** (estos dependen de la paleta activa del archivo).
    

##### Cómo aplicarlos

Los colores se colocan **entre corchetes `[]` al inicio de cada sección** del formato.

Recuerda que la estructura del formato es:

```
[Positivo];[Negativo];[Cero];[Texto]
```

Ejemplos:

1. **Negativos en rojo**
    

```
#,##0;[Red](#,##0)
```

- 1234 → `1,234`
    
- -1234 → `(1,234)` en rojo
    

2. **Positivos verdes, negativos rojos, ceros azules**
    

```
[Green]#,##0;[Red]-#,##0;[Blue]0
```

- 1200 → verde
    
- -800 → rojo
    
- 0 → azul
    

3. **Texto en magenta**
    

```
#,##0;[Red]-#,##0;0;[Magenta]@
```

- Si escribes un número se ve normal (verde/rojo según el caso).
    
- Si escribes texto, aparece en magenta.
    

4. **Usando índices de color**
    

```
[Color10]#,##0;[Color3]-#,##0;[Color5]0
```

- El color depende de la paleta de tu Excel.
    

##### Tips útiles

- Puedes mezclar colores con símbolos y formatos.
    
- No puedes usar valores hexadecimales (#FF0000, etc.), solo nombres o índices.
    
- Si usas nombres en español como `[Rojo]`, Excel no lo reconoce: siempre deben ser en **inglés** si usas Excel en Inglés.
    
- En números con 2 secciones, el color del primero aplica a positivos y ceros.
    

👉 Ejemplo completo con las 4 secciones:

```
[Blue]#,##0;[Red]-#,##0;[Green]0;[Magenta]@
```

- Positivos → azul
    
- Negativos → rojo
    
- Ceros → verde
    
- Texto → magenta
    

#### Colores + Condicionales

Esto es distinto al **Formato condicional** de Excel (el que está en la pestaña **Inicio → Formato condicional**).  
En **formato personalizado**, las condiciones **solo cambian la apariencia en la celda**, no permiten acciones más complejas.

##### Sintaxis general con condiciones en formatos personalizados

```
[color][condición]formato;[color][condición]formato;formato_si_no_cumple
```

- **[condición]** → Comparación numérica: `<`, `<=`, `>`, `>=`, `=`, `<>`.
    
- **[color]** → Uno de los colores permitidos (`Red`, `Green`, `Blue`, etc.).
    
- Puedes poner hasta **2 condiciones**, luego una sección “por defecto”.
    

##### Ejemplos prácticos

1. Números menores a 100 en rojo, mayores o iguales en azul

```
[Red][<100]#,##0;[Blue][>=100]#,##0
```

- 50 → se muestra rojo
    
- 150 → se muestra azul
    

2. Tres rangos (ejemplo semáforo)

Menor a 0 → rojo, entre 0 y 100 → azul, mayor a 100 → verde.

```
[Red][<0]#,##0;[Blue][<=100]#,##0;[Green]#,##0
```

- -10 → rojo
    
- 50 → azul
    
- 200 → verde
    

3. Positivos en verde, negativos en rojo, ceros en amarillo

```
[Green][>0]#,##0;[Red][<0]#,##0;[Yellow]0
```

4. Mostrar texto con color fijo, pero números con condiciones

```
[Red][<0]#,##0;[Blue]#,##0;0;[Magenta]@
```

- Negativos → rojos
    
- Positivos o ceros → azules
    
- Texto → magenta
    

##### 📌 Limitaciones importantes

- Solo se pueden usar **dos condiciones explícitas**, más una tercera sección como “catch-all”.
    
- Si intentas poner más de 2 condiciones, Excel ignora las demás.
    
- No se puede usar fórmulas complejas (ej: `[<A1]` no es válido, deben ser valores fijos).
    
- No afecta la lógica de la celda, solo cómo se ve.
    

#### Moneda

En Excel, "Moneda en Formato Personalizado" se refiere a la opción de crear un formato numérico específico para valores monetarios, donde tú defines el símbolo, la posición de los decimales y los separadores, o utilizas formatos ya existentes como el de "Moneda" o "Contabilidad" que se ajustan a la configuración regional para mostrar valores con un signo monetario y decimales. 

¿Qué es el formato de moneda en Excel?

- Es un formato que se aplica a los números para que se muestren con un símbolo de moneda (como $, €, ¥) y para definir el número de posiciones decimales y el uso de separadores de miles. 
- Existe el formato predefinido de "Moneda", que alinea el símbolo junto al primer dígito de la celda. 
- También está el formato de "Contabilidad", que alinea el símbolo de moneda con las posiciones decimales en una columna. 

![Currency](https://i.postimg.cc/BvML683S/1-2-currency.png)

![Quick access to currency](https://i.postimg.cc/Dw71w3Gd/1-2-quick-access-to-currency.png)

#### Notación científica

Es una forma de escribir números muy grandes o muy pequeños usando **potencias de 10**.  
La idea es expresar un número como:

$`n = a \times 10^b`$

donde:

- (a) = mantisa (un número entre 1 y 10, con decimales)
    
- (b) = exponente (cuántas veces mover la coma decimal).
    

##### Cómo funciona en Excel

En Excel, el formato de notación científica se escribe con **E** (de "exponent"):

- **0.00E+00** → dos decimales en la mantisa, exponente con dos dígitos.
    
- **##0.0E+0** → un decimal en la mantisa, exponente con un dígito.
    

##### Ejemplo práctico

Número: **300000**

1. Representación científica:    
    $`300000 = 3.00 \times 10^5`$
    
2. En Excel con formato **0.00E+00** →  
    `3.00E+05`
    
3. Si usas **0.0E+00** →  
    `3.0E+05`
    
4. Si usas **##0.0E+0** →  
    `300.0E+3` (porque ese formato obliga a que la parte antes de la E tenga al menos 3 dígitos).
    

##### Ejemplos con diferentes valores

- **0.00045** con formato **0.00E+00** → `4.50E-04`
    
- **987654321** con formato **0.00E+00** → `9.88E+08`
    
- **12.3** con formato **0.00E+00** → `1.23E+01`
    

##### Personalización

- Los **ceros después del punto** controlan cuántos decimales aparecen en la mantisa.
    
    - `0E+00` → sin decimales.
        
    - `0.00E+00` → dos decimales.
        
    - `0.000E+00` → tres decimales.
        
- Los ceros después de la **E** controlan cuántos dígitos muestra el exponente.
    
    - `0.00E+0` → exponente con 1 dígito.
        
    - `0.00E+00` → exponente con 2 dígitos (ej: E+05).
        







https://youtu.be/rdRtDDV0-rg?t=1715



## Colors

`#090b10`
`#0f111a`
`#4f46e5`

`alt 126 ~`

## Math

This sentence uses $\` and \`$ delimiters to show math inline: $`\sqrt{3x-1}+(1+x)^2`$