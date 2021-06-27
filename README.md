## Run app docker-compose (Linux)
1. Install Docker and Docker Compose.
2. Create `.env` from `.env.example`.
3. Set env variables :
```bash
source .env
```
4. Run tests:
```bash
sudo docker-compose build
sudo docker-compose run web_app sh -c "cd weather/; pytest"
```
Tests taks ~4 min to run.


## Services

Start running the service
```bash
sudo docker-compose up
```

Use a http client and make http request to the following services

### Collect data
POST `http://localhost:8000/collection-request/` 

BODY : 
```
{
    "id" : 1
}
```
example response(takes ~3min to complete) :
```
{
    "value": "OK"
}
```

### Check progress
GET `http://localhost:8000/collection-request/{id}/progress` 

example response :
```
{
    "result": 0.3592814371257485
}
```

### Inpect fully collected data
GET `http://localhost:8000/collection-request/{id}` 

example response :
```
{
    "id":1,
    "created_at":"2021-06-27T01:55:00.255890Z",
    "city_weather_info":[
        {
            "city_id":3440781,
            "humidity":91,
            "temperature":9.87
        },
        {
            "city_id":3441243,
            "humidity":83,
            "temperature":7.56
        },
        ...
    ]
}
```