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

## Lista de videos [GET /videos/]

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

## Reproducir video almacenado [GET /videos/{id}/reproducir]

+ Parameters
    + id (int) ID Video

+ Response 200 (application/json)

        {
            "id": 1,
            "inicio_transmision": "05-09-2015 11:00",
            "fin_transmision": "06-09-2015 12:00",
            "tamano_video": "1 GB",
            "descargar_video": "http://ejemplo/download/video_1"
            "source_video":"http//ejemplovideo/replay/1"
        }
        
# Camaras [/camaras/{?id}]

+ Parámetros
    + id (int) ID Cámara
    + marca
    + brillo
    + calidad
    + color
    + contraste
    + ip
    + coodenadas

## Lista de cámaras [GET /camaras/]

+ Response 200 (application/json)

        {
            "camaras": [
                {
                    "id": 1,
                    "marca":"Camara x HD Pro 1",
                    "fecha_add":"05-09-2015",
                    "ip":"192.168.1.100",
                    "latitud":"-33.000101",
                    "longitud":"-77.01212",
                    "configuración":{
                        "brillo": 10,
                        "calidad": "720p",
                        "color":"rgba(0,0,0)",
                        "contraste":"30"
                    }
                },{
                    "id": 1,
                    "marca":"Camara x HD Pro 1",
                    "fecha_add":"05-09-2015",
                    "ip":"192.168.1.101",
                    "latitud":"-33.000101",
                    "longitud":"-77.01212",
                    "configuración":{
                        "brillo": 10,
                        "calidad": "720p",
                        "color":"rgba(0,0,0)",
                        "contraste":"30"
                    }
                }
            ]
        }

## Buscar Cámara [GET /camaras/{id}]

+ Response 200 (application/json)

        {
            "id": 1,
            "marca":"Camara x HD Pro 1",
            "fecha_add":"05-09-2015",
            "ip":"192.168.1.100",
            "latitud":"-33.000101",
            "longitud":"-77.01212",
            "configuración":{
                "brillo": 10,
                "calidad": "720p",
                "color":"rgba(0,0,0)",
                "contraste":30
            }
        }
+ Response 404 (application/json)

        { 
            "error": "Recurso no se encuentra" 
        }

### Editar Cámara [PATCH /camaras/{id}]

+ Request (application/json)

        {
            "brillo": 20,
            "contraste": 20,
        }

+ Response 200

        {
            "id": 1,
            "marca":"Camara x HD Pro 1",
            "fecha_add":"05-09-2015",
            "ip":"192.168.1.100",
            "latitud":"-33.000101",
            "longitud":"-77.01212",
            "configuración":{
                "brillo": 20,
                "calidad": "720p",
                "color":"rgba(0,0,0)",
                "contraste":20
            }
        }

+ Response 404

        { 
            "error": "Recurso no disponible"
        }

+ Response 400

        { 
            "error": "Fallo al modificar el Recurso"
        }
        
## Eliminar Cámara [DELETE /camaras/{id}]

+ Response 200

        { 
            "result": True,
            "message": "Cámara eliminada con éxito"
        }

## Nuevo Cámara [POST /camaras]

+ Request (application/json)

        {
            "marca":"Camara x HD Pro 2",
            "fecha_add":"05-09-2015",
            "brillo": 10,
            "calidad": "720p",
            "color":"rgba(0,0,0)",
            "contraste":30
            
        }
        
+ Response 201

        {
            "id": 2,
            "marca":"Camara x HD Pro 2",
            "fecha_add":"05-09-2015",
            "ip":"192.168.1.100",
            "latitud":"-33.000101",
            "longitud":"-77.01212",
            "configuración":{
                "brillo": 10,
                "calidad": "720p",
                "color":"rgba(0,0,0)",
                "contraste":30
            }
        }
        
# Transmitir video [GET /camaras/{id}/transmitir]

+ Response 200

        {
            "id": 1,
            "marca":"Camara x HD Pro 1",
            "fecha_add":"05-09-2015",
            "ip":"192.168.1.100",
            "latitud":"-33.000101",
            "longitud":"-77.01212",
            "configuración":{
                "brillo": 10,
                "calidad": "720p",
                "color":"rgba(0,0,0)",
                "contraste":"30"
            },
            "Video":{
                "id": 1,
                "descargar_video": "http://ejemplo/download/video_1"
            },
            "broadcast":{
                "id": 1,
                "inicio_broadcast":"05-09-2015 18:00",
                "descripción": "Descripción video tiempo real",
                "source":"http://ejemplo/broadcast/1/play",
                "fps":30
            }
        }
