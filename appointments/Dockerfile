FROM python:3.9-slim

WORKDIR /app

RUN pip install flask

COPY . /app

EXPOSE 7070

CMD ["python", "app.py"]