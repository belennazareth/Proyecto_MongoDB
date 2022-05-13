- Consultas de datos simples:
    * Busca el pez de nombre Sea Bass cuyo precio es de 400 bayas.

            db.fishes.find({"name":"Sea Bass"},{"price":400})

        ![](/screenshots/consulta1.png)

    * Contar los peces que hay de río con precio menor de 500 bayas.

            db.fishes.find({"location":"River"},{"price":{$lt:500}}).count()

        ![](/screenshots/captura2.png)

    * Mostrar los nombres de los peces con el tamaño de sombra más pequeño (smallest).

            

    * Obtener los 3 primeros peces cuyo nombre empiece por A.
    * Obtener los precios de los peces cuyos id estén entre 70 y 80, los precios deben estar ordenados de menor a mayor.

- Consultas con arrays: 
    * Crea un array al pez koi donde se almacenarán los colores naranja, blanco, amarillo y negro.
    * Actualiza las horas del pez con id igual a dos añadiendo las cuatro y las cinco.
    * Eliminar las horas 5,6 y 7 del pez con id 16.
    

- Consultas con documentos embebidos:
    * Obtener todos los peces que aparecen únicamente de septiembre a noviembre en el norte.
    * Obtener el id de los peces que tengan como texto "May-October" en la zona norte, ten en cuenta que el texto se encuentra dentro de meses y a su vez dentro de zona norte.
    * Eliminar los peces que contengan como texto en el tiempo "9 p.m. - 4 a.m.".

- Consulta de agrupación:
    * Obten el numero de peces agrupados por precio ordenados de mayor a menor.