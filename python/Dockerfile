FROM python:3.10-alpine

WORKDIR /app

RUN python -m venv ./.venv

COPY . .

RUN pip install --no-cache-dir -r dock.txt

COPY dock.txt .

EXPOSE 8080

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]