FROM python:3.10-slim

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY dock.txt .

RUN pip install --no-cache-dir -r deps.txt

# Копіюємо код
COPY . .

EXPOSE 8080

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]
