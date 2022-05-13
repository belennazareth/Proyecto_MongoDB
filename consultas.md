- Consultas de datos simples:
    * Busca el pez de nombre Sea Bass cuyo precio es de 400 bayas.

            db.fishes.find({"name":"Sea Bass"},{"price":400})

        ![](/screenshots/consulta1.png)

    * Contar los peces que hay de río con precio menor de 500 bayas.

            db.fishes.find({"location":"River"},{"price":{$lt:500}}).count()

        ![](/screenshots/captura2.png)

    * Mostrar los nombres de los peces con el tamaño de sombra más pequeño (smallest).

            db.fishes.find({"shadow_size": "Smallest"},{"name":1})

        ![](/screenshots/captura3.png)

    * Obtener los 3 primeros peces cuyo nombre empiece por A.

            db.fishes.find({"name":/A/},{"name":1}).limit(3)

        ![](/screenshots/captura4.png)

    * Obtener los precios de los peces cuyos id estén entre 70 y 80, los precios deben estar ordenados de menor a mayor.

            db.fishes.find({"id":{$gte:70,$lte:80}},{"price":1}).sort({"price":1})


        ![](/screenshots/captura5.png)

- Consultas con arrays: 

    * Crea un array al pez koi donde se almacenarán los colores naranja, blanco, amarillo y negro.

            db.fishes.update({ "name": "Koi" },{$push:{"color":["Naranja", "Amarillo", "Blanco", "Negro"]}})

        
        ![](/screenshots/consulta6.png)

    * Actualiza las horas del pez con id igual a dos añadiendo las cuatro y las cinco.

            db.fishes.update(
                {"id":2},
                {$push:{array:
                {$each:[9,10,11,12,13,14,15,16,17]
                }
                }
            })

        ![](/screenshots/consulta7.png)

    * Eliminar las horas 5,6 y 7 del pez con id 16.
    
            db.fishes.update({"id":16},{$push:{array:{$each:[0, 1, 2, 3, 4, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23]}}})

        ![](/screenshots/captura8.png)

- Consultas con documentos embebidos:
    * Obtener todos los peces que aparecen únicamente de septiembre a noviembre en el norte.

            db.fishes.find({"months.northern.text":"September - November"},{"name":1})

        ![](/screenshots/captura9.png)

    * Obtener el id de los peces que tengan como texto "May-October" en la zona norte, ten en cuenta que el texto se encuentra dentro de meses y a su vez dentro de zona norte.

            db.fishes.find({"months.northern.text":"May-October"},{"id":1})

        ![](/screenshots/captura10.png)

    * Eliminar los peces que contengan como texto en el tiempo "9 p.m. - 4 a.m.".

            db.fishes.deleteMany({"times.text":"9 p.m. - 4 a.m."})

        ![](/screenshots/captura11.png)

- Consulta de agrupación:
    * Obten el numero de peces agrupados por precio ordenados de mayor a menor.

            db.fishes.aggregate([{$group: {"id":"price",count:{$sum:1}}}])