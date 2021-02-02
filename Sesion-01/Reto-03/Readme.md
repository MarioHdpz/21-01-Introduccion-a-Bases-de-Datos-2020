[`Introducción a Bases de Datos`](../../Readme.md) > [`Sesión 01`](../Readme.md) > `Reto 3`
	
## Reto 3: Ordenamientos y Límites

<div style="text-align: justify;">

### 1. Objetivos :dart:

- Escribir consultas que permitan responder a algunas preguntas mediante ordenamientos y límites.

### 2. Requisitos :clipboard:

1. MySQL Workbench instalado.

### 3. Desarrollo :rocket:


Usando la base de datos `kavak`, escribe las consultas que permita responder las siguientes preguntas.

1. ¿De que año es el auto más antiguo?
1. ¿Cuál son los 3 autos con mayor kilometraje?
1. ¿Cuál es el auto que lleva más tiempo sin venderse?

<details><summary>Solución</summary>
<p>

   ```sql
   SELECT name, year
   FROM car
   ORDER BY year 
   LIMIT 1;
   ```

   ```sql
   SELECT name, km
   FROM car
   ORDER BY km DESC
   LIMIT 3;
   ```

   ```sql
   SELECT name, post_date
   FROM car
   ORDER BY post_date
   LIMIT 1;
   ```

</p>
</details> 

<br/>

[`Anterior`](../Ejemplo-04/Readme.md) | [`Siguiente`](../Readme.md#3-proyecto-hammer)

</div>
