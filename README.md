# Sistema control de tráfico urbano
Prototipo para el sistema de control de tráfico urbano

URL API: http://private-92a6b-diegovalladares.apiary-mock.com/ <br/>
Github: https://github.com/dvdeveloper/apiary-TraficoUrbano

## API Blueprint

+ [Documentación API](http://docs.diegovalladares.apiary.io/)

# Videos [/videos/{?id}]

+ Parámetros
    + id (int) ID Video
    + inicio_transmision (datetime)

## Lista de videos [GET]

+ Response 200 (application/json)

        {
            "videos": [
                {
                    "id": 1,
                    "inicio_transmision": "05-09-2015 11:00",
                    "fin_transmision": "06-09-2015 12:00",
                    "tamano_video": "1 GB",
                    "descargar_video": "http://ejemplo/download/video_1"
                },
                {
                    "id": 2,
                    "inicio_transmision": "05-09-2015 11:00",
                    "fin_transmision": "06-09-2015 12:00",
                    "tamano_video": "1 GB",
                    "descargar_video": "http://ejemplo/download/video_2"
                },{
                    "id": 3,
                    "inicio_transmision": "05-09-2015 11:00",
                    "fin_transmision": "06-09-2015 12:00",
                    "tamano_video": "1 GB",
                    "descargar_video": "http://ejemplo/download/video_3"
                }
            ]
        }

## Buscar video [GET /videos/{id}]
Buscar video por su identificador único (ID)

+ Parameters
    + id (int) ID Video

+ Response 200 (application/json)

        {
            "id": 1,
            "inicio_transmision": "05-09-2015 11:00",
            "fin_transmision": "06-09-2015 12:00",
            "tamano_video": "1 GB",
            "descargar_video": "http://ejemplo/download/video_1"
        }

## Eliminar video [DELETE /videos/{id}]

+ Parameters
    + id (int) ID Video

+ Response 200 (application/json)

        {
            "result": True,
            "message": "Video eliminado con éxito"
        }
