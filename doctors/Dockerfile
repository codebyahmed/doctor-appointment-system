FROM python:3.9-slim

WORKDIR /app

RUN pip install flask

COPY . /app

EXPOSE 9090

CMD ["python", "app.py"]