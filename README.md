## Run app docker-compose (Linux)
1. Install Docker and Docker Compose.
2. Create `.env` from `.env.example`.
3. Set env variables :
```bash
source .env
```
4. Start services:
```bash
sudo docker-compose up -d

sudo docker-compose down # stop services
sudo docker-compose ps # inspect services
```

5. Go to service:
- `http://localhost:8000/` 
