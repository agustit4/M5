/*=========================
READ ME 
=========================
1) ¿Cuántas filas devuelve cada consulta y por qué son distintas?
Consulta con UNION: devuelve 11 filas.
Consulta con UNION ALL: devuelve 14 filas.

Ambas consultas son diferentes ya que:
- Por un lado, UNION combina los resultados de ambas tablas eliminando los duplicados (las filas que cuentan con coincdencias exactas entre ID del producto y el producto en sí). 
- Mientras que UNION ALL no elimina los duplicados, por lo que el conteo final es mayor. 

Ejemplos concretos:
- En el resultado de UNION ALL aparecen productos repetidos como Monitor 4K 27", Teclado Mecánico, SSD Externo 1TB.
- En el resultado de UNION, las repeticiones mencionadas ya no aparecen si cuentan con coincidencias tanto en el ID del producto como en el nombre. 

Por eso UNION termina dando menos filas (11) que UNION ALL (14).

2) ¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?

UNION ALL es más eficiente porque no trabaja eliminando duplicados sino que concatena los resultados de ambas consultas. UNION realiza este paso adicional para eliminar duplicados.

3) ¿En qué casos de negocio usarías cada uno? Dá al menos dos ejemplos reales distintos a los del ejercicio.

Usaría UNION ALL cuando necesite, por ejemplo, sumar tickets de venta de Norte y Sur para analizarlos por fecha y hora. Incluso analizar tendencias de consumo con IA (la repetición en estos casos es fundamental).

Usaría UNION cuando requiera una lista de datos únicos, por ejemplo, una lista de IDs de productos o de clientes. 

4) ¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?

Si las columnas no coinciden en cantidad o tipos entre ambas consultas, SQL no puede “unir” las filas correctamente.

Usualmente genera un error como “The column counts do not match” (o equivalente): cuando no coincide la cantidad de columnas.
“datatype mismatch” / “Operand type clash” (o equivalente): cuando no coinciden tipos entre las columnas correspondientes.
