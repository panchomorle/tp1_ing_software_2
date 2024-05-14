# TP1 Ingeniería del Software II

*Alumnos integrantes:*
---
Camargo, Amir.
Jiance, Kiara.
Melero, Tania.
Morales, Juan P.
Sebestyen, Kiara.


## VALIDACIONES:

| Atributo                | Validación                                                                                                                                                                                                                                       |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Código de producto      | Tipo de dato: VARCHAR; No debe existir en el sistema previamente; Debe tener 8 caracteres; Los 2 primeros caracteres deben ser letras; Los últimos 6 caracteres deben ser casteables a INTEGER; No se deben aceptar caracteres no alfanuméricos. |
| Nombre de producto      | Tipo de dato: VARCHAR; Limitado a 255 caracteres.                                                                                                                                                                                                |
| Descripción de producto | Tipo de dato: TEXT;                                                                                                                                                                                                                              |
| Stock inicial           | Tipo de dato: INTEGER; Debe ser mayor que cero.                                                                                                                                                                                                  |
| Punto de pedido         | Tipo de dato: INTEGER; Debe ser mayor que cero.                                                                                                                                                                                                  |
| Fecha de compra         | Tipo de dato: DATE; Debe ser una fecha menor a la fecha actual.                                                                                                                                                                                  |
| Código de proveedor     | Tipo de dato: INTEGER; No debe existir en el sistema previamente; Debe ser mayor o igual a cero.                                                                                                                                                 |
| Precio de compra        | Tipo de dato: FLOAT; Debe ser mayor o igual a cero.                                                                                                                                                                                              |


## CODIFICACIÓN:
#### PRODUCTOS:
Para la codificación de los **productos** elegimos un tipo de código de origen alfabético con el siguiente formato: **A-A-00-0000**
- Donde la primer A representa la categoría de sexo (M/F/X) del producto pedido por el cliente.
- La segunda A representa el tipo de prenda ("R" para las Remeras, "P" para los Pantalones)
- Los dos números siguientes representan el talle (del 00 al 99)
- Los últimos cuatro números son el código único del producto. (del 0000 al 9999)

#### PROVEEDORES:
Para la codificación de los **proveedores** elegimos la codificación secuencial simple, debido a que el código del proveedor no es un dato que trascenderá al sistema (los usuarios no necesitan recordarlo), sino que será manejado internamente.
En la base de datos, a grandes rasgos, se vería así:

| codigo_proveedor | nombre_proveedor |
| :--------------: | ---------------- |
|        1         | Fulano           |
|        2         | Mengano          |
|        3         | Leopoldino       |
|        4         | Amito            |
