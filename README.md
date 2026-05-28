# NEXA-Atlas

Production Commands
bash
# Start with 8 workers for high load
uvicorn nexa_atlas_v6:app --host 0.0.0.0 --port 8080 --workers 8

# With Docker
docker build -t nexa-atlas .
docker run -p 8080:8080 nexa-atlas

# Load testing
ab -n 1000 -c 100 http://localhost:8080/chat -p test.json -T application/json
