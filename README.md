# Actividad-ANTL-25-2

Calculadora de expresiones aritméticas implementada con ANTLR 4 en Java. Soporta suma, resta, multiplicación, división, paréntesis y variables.

## Archivos del proyecto

| Archivo | Descripción |
|---|---|
| `LabeledExpr.g4` | La gramática — define qué expresiones son válidas y cómo se estructuran |
| `EvalVisitor.java` | La lógica de la calculadora — evalúa cada expresión del árbol sintáctico |
| `Calc.java` | El main — conecta el lexer, parser y visitor para correr el programa |
| `t.expr` | Archivo de prueba con expresiones de ejemplo |

## Cómo compilar y ejecutar

### 1. Generar el lexer y parser con ANTLR
```bash
antlr4 -no-listener -visitor LabeledExpr.g4
```
Esto genera automáticamente: `LabeledExprLexer.java`, `LabeledExprParser.java`, `LabeledExprVisitor.java`, `LabeledExprBaseVisitor.java`.

### 2. Compilar todo
```bash
javac Calc.java EvalVisitor.java LabeledExpr*.java
```

### 3. Ejecutar
```bash
# Con archivo de entrada
java Calc t.expr

```

## Ejemplo

Dado el archivo `t.expr`:
```
193
a = 5
b = 6
a+b*2
(1+2)*3
```

Salida:
```
193
17
9
```

## Qué puede calcular

```
5 + 3        → suma
10 - 4       → resta
6 * 7        → multiplicación
20 / 4       → división
(1+2)*3      → paréntesis
a = 5        → asignar variable
a + 10       → usar variable
```
