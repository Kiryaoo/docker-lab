FROM python:3.10-alpine

RUN apk add --no-cache \
    build-base \
    libffi-dev \
    musl-dev \
    gcc \
    python3-dev \
    jpeg-dev \
    zlib-dev \
    curl


RUN python3 -m ensurepip && pip install --upgrade pip

WORKDIR /app

COPY dock.txt .

COPY . .

RUN pip install --no-cache-dir -r dock.txt

EXPOSE 8080

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]