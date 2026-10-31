# Hospital San Gabriel — Análisis de registros clínicos simulados

## Objetivo
Organizar y analizar una base de datos **ficticia** de 20 registros clínicos con fines académicos. El ejercicio permite practicar limpieza de datos, cálculo de indicadores descriptivos, identificación de inconsistencias y reflexión sobre la privacidad clínica. No es un sistema hospitalario real ni debe utilizarse para tomar decisiones médicas.

## Diccionario de datos

| Campo | Descripción | Tipo / formato esperado |
|---|---|---|
| `código` | Identificador ficticio del registro (P001–P020). | Texto |
| `edad` | Edad simulada de la persona registrada. | Entero, años |
| `sexo` | Categoría registrada en la base (`F` o `M`). | Categórico |
| `fecha de consulta` | Fecha simulada de consulta. | Fecha `DD/MM/AAAA` |
| `motivo` | Motivo de consulta simulado. | Texto |
| `temperatura (°C)` | Temperatura corporal simulada. | Numérico, °C |
| `frecuencia cardíaca (lpm)` | Frecuencia cardíaca simulada. | Numérico, latidos por minuto |
| `saturación de oxígeno (%)` | Saturación de oxígeno simulada. | Numérico, porcentaje; puede estar ausente |
| `diagnóstico simulado` | Etiqueta diagnóstica creada para el ejercicio. | Texto |
| `estado de atención` | Estado del proceso (`Finalizada`, `Pendiente`, `En atención`). | Categórico |

## Proceso de limpieza
1. Se identificaron las filas correspondientes a pacientes mediante el patrón de código `P` seguido de tres dígitos.
2. Se excluyeron las filas vacías y el resumen estadístico que aparecía mezclado debajo de la tabla de pacientes.
3. Se normalizaron los encabezados, eliminando espacios al inicio/final y caracteres invisibles.
4. Se convirtieron edad, temperatura, frecuencia cardíaca y saturación a variables numéricas; para la saturación se retiró el símbolo `%`.
5. Se conservaron los datos faltantes como ausentes, sin inventar valores. Se identificó que P016 no tiene saturación registrada.
6. Se revisaron los indicadores calculados y se señalaron inconsistencias del resumen original, especialmente la suma de saturación reportada como `18,43`.

## Indicadores revisados
- Total de registros: 20
- Edad promedio: 43.0 años
- Temperatura promedio: 37.145 °C
- Distribución registrada por sexo: 10 F y 10 M
- Estado de atención: 9 finalizadas, 4 pendientes y 7 en atención
- Saturación mínima disponible: 91%
- Registros con al menos un dato faltante: 1

## Archivos entregados
- `README.md`: objetivo del repositorio, diccionario de datos, proceso de limpieza, indicadores principales y declaración de datos ficticios.
- `analisis.md`: interpretación de los siete indicadores, inconsistencias detectadas y reflexión sobre privacidad clínica.
- `Libro1.csv`: archivo de datos proporcionado y usado como fuente de análisis.
- `Base_Datos_Hospital (1).xlsx`: archivo proporcionado originalmente; pese a la extensión `.xlsx`, su contenido es texto delimitado por punto y coma, no un libro Excel válido. Se recomienda volver a exportarlo correctamente como `.xlsx` o guardarlo con extensión `.csv`.

## Declaración de datos ficticios
Todos los registros, identificadores, motivos de consulta, signos vitales, diagnósticos y estados incluidos en este ejercicio son **ficticios y creados con fines académicos**. No representan pacientes reales. Aun así, se aplican principios de privacidad y manejo responsable de datos para practicar procedimientos adecuados de análisis.
