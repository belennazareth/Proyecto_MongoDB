 * Con la utilidad mongoimport introduce los documentos correspondientes a esa colección

         mongoimport --db acfish --collection fishes --jsonArray --file github/Proyecto_MongoDB/animalcrossing_fish.json 

 * Insertar varios documentos utilizando los dos métodos de inserción de MongoDB

        use acfish

        db.fishes.insertOne({
            "id": 81,
            "name": "fish1",
            "location": "River",
            "shadow_size": "Smallest",
            "price": 500,
            "times": {
                "array": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23],
                "text": "All Day"
            },
            "months": {
                "northern": {
                    "array": [1, 2, 3, 11, 12],
                    "text": "November - March"
                },
                "southern": {
                    "array": [5, 6, 7, 8, 9],
                    "text": "May - September"
                }
            }
        })

        db.fishes.insertMany(
            [
                {
                    "id": 82,
                    "name": "fish2",
                    "location": "Sea",
                    "shadow_size": "Small",
                    "price": 15000,
                    "times": {
                        "array": [
                            0,
                            1,
                            2,
                            3,
                            21,
                            22,
                            23
                        ],
                        "text": "9 p.m. - 4 a.m."
                    },
                    "months": {
                        "northern": {
                            "array": [
                                1,
                                2,
                                3,
                                4,
                                5,
                                6,
                                7,
                                8,
                                9,
                                10,
                                11,
                                12
                            ],
                            "text": "Year Round"
                        },
                        "southern": {
                            "array": [
                                1,
                                2,
                                3,
                                4,
                                5,
                                6,
                                7,
                                8,
                                9,
                                10,
                                11,
                                12
                            ],
                            "text": "Year Round"
                        }
                    }
                },
                {
                    "id": 83,
                    "name": "fish3",
                    "location": "Sea (rainy days)",
                    "shadow_size": "Largest",
                    "price": 15000,
                    "times": {
                        "array": [
                            0,
                            1,
                            2,
                            3,
                            4,
                            5,
                            6,
                            7,
                            8,
                            9,
                            10,
                            11,
                            12,
                            13,
                            14,
                            15,
                            16,
                            17,
                            18,
                            19,
                            20,
                            21,
                            22,
                            23
                        ],
                        "text": "All day"
                    },
                    "months": {
                        "northern": {
                            "array": [
                                1,
                                2,
                                3,
                                4,
                                5,
                                6,
                                7,
                                8,
                                9,
                                10,
                                11,
                                12
                            ],
                            "text": "Year Round"
                        },
                        "southern": {
                            "array": [
                                1,
                                2,
                                3,
                                4,
                                5,
                                6,
                                7,
                                8,
                                9,
                                10,
                                11,
                                12
                            ],
                            "text": "Year Round"
                        }
                    }
                }
            ]
        )

    - InsertOne():
    ![](/screenshots/insertone.png)
    - InsertMany():
    ![](/screenshots/insertmany.png)
    
 * Elimina varios documentos utilizando los dos métodos de eliminación de MongoDB

 * Actualiza varios documentos utilizando los tres métodos de eliminación de MongoDB