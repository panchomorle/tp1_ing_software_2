# TP1 Ingeniería del Software II

*Alumnos integrantes:*
- Camargo, Amir.
- Jiance, Kiara.
- Melero, Tania.
- Morales, Juan P.
- Sebestyen, Kiara.


## VALIDACIONES:

| Atributo                | Validación                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Código de producto      | Tipo de dato: VARCHAR; No se deben aceptar caracteres no alfanuméricos (el código se compone únicamente de letras y números); No debe existir en el sistema previamente (para cumplir con la unicidad); No puede estar vacío (para cumplir con la existencia); Debe tener estrictamente 8 caracteres, los 2 primeros deben ser letras y los 6 últimos deben ser casteables a INTEGER (para cumplir con el formato establecido). |
| Nombre de producto      | Tipo de dato: VARCHAR; Limitado a 255 caracteres como máximo (no se necesita más que eso para un nombre);                                                                                                                                                                                                                                                                                                                       |
| Descripción de producto | Tipo de dato: TEXT;                                                                                                                                                                                                                                                                                                                                                                                                             |
| Stock inicial           | Tipo de dato: INTEGER; No puede estar vacío (es un dato necesario).                                                                                                                                                                                                                                                                                                                                                             |
| Punto de pedido         | Tipo de dato: INTEGER; No puede estar vacío (es un dato necesario).                                                                                                                                                                                                                                                                                                                                                             |
| Fecha de compra         | Tipo de dato: DATE; Debe ser una fecha menor a la fecha actual (no puede haber sido comprado en el futuro); No puede estar vacío (es un dato necesario).                                                                                                                                                                                                                                                                        |
| Proveedor               | No puede estar vacío (todo producto debería tener un proveedor).                                                                                                                                                                                                                                                                                                                                                                |
| Precio de compra        | Tipo de dato: FLOAT; Debe ser mayor o igual a cero (puede haber sido obtenido con coste 0, pero no puede haber sido obtenido a un precio negativo); No puede estar vacío (todo producto fue comprado por un precio determinado).                                                                                                                                                                                                |


## CODIFICACIÓN:
#### PRODUCTOS:
Para la codificación de los **productos** elegimos un tipo de código de origen alfabético con el siguiente formato: **A-A-00-0000**
- Donde la primer A representa la categoría de sexo (M/F/X) del producto pedido por el cliente.
- La segunda A representa el tipo de prenda ("R" para las Remeras, "P" para los Pantalones)
- Los dos números siguientes representan el talle (del 00 al 99)
- Los últimos cuatro números son el código único del producto. (del 0000 al 9999)
Los componentes del código, luego de que el código sea validado, irán a nuestra tabla de **productos** como una clave primaria compuesta.

| cod_sexo | cod_tipo | cod_talle | cod_numero |
| :------: | -------- | --------- | ---------- |
|    M     | R        | 40        | 0012       |
|    M     | R        | 46        | 0012       |
|    F     | P        | 38        | 0125       |
|    X     | R        | 20        | 0012       |
*prototipo de clave primaria de la tabla "productos"*

Como se puede observar, este tipo de codificación nos permite clasificar y ordenar las prendas de manera sencilla e intuitiva sin perder la condición de unicidad de cada producto dentro del sistema.

#### PROVEEDORES:
Para la codificación de los **proveedores** elegimos la codificación secuencial simple, debido a que el código del proveedor no es un dato que trascenderá al sistema (los usuarios no necesitan recordarlo), sino que será manejado internamente.
En la base de datos, a grandes rasgos, se vería así:

| codigo_proveedor | nombre_proveedor |
| :--------------: | ---------------- |
|        1         | Fulano           |
|        2         | Mengano          |
|        3         | Leopoldino       |
|        4         | Amito            |

