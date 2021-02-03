[`Introducción a Bases de Datos`](../../Readme.md) > [`Sesión 02`](../Readme.md) > `Reto 4`
	
## Reto 4: Subconsultas

<div style="text-align: justify;">

### 1. Objetivos :dart:

- Escribir consultas que permitan responder a algunas preguntas.

### 2. Requisitos :clipboard:

1. MySQL Workbench instalado.

### 3. Desarrollo :rocket:

Usando la base de datos `kavak` resuelve los siguientes ejercicios.

- Muestra cuántos autos se venden en total en la Ciudad de México y Guadalajara.
- Muestra el nombre de la marca y el número de autos que hay por cada una de ellas.
- Muestra el promedio de autos por año.

<details><summary>Solución</summary>
<p>

- Muestra cuántos autos se venden en total en la Ciudad de México y Guadalajara.

   ```sql
   SELECT
   COUNT(*)
   FROM kavak.car
   WHERE region_id IN (
   SELECT id FROM kavak.region 
   WHERE name IN ("Ciudad de México", "Puebla")
   );
   ```


- Muestra el nombre de la marca y el número de autos que hay por cada una de ellas.

   ```sql
   SELECT 
   (SELECT name FROM kavak.make WHERE id = make_id) AS make,
   COUNT(*) AS count
   FROM kavak.car
   GROUP BY make_id;
   ```

   
- Muestra el promedio de autos por año

   ```sql
   SELECT AVG(count) FROM (
	SELECT year, COUNT(*) AS count
    FROM kavak.car GROUP BY year
   ) AS cars_per_year;
   ```

</p>
</details> 

<br/>

[`Anterior`](../Ejemplo-04/Readme.md) | [`Siguiente`](../Readme.md#3-proyecto-hammer)            

</div>
