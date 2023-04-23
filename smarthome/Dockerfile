FROM --platform=$BUILDPLATFORM python:3.10-alpine AS builder
EXPOSE 8080
WORKDIR /app 
COPY requirements.txt /app
RUN pip3 install -r requirements.txt --no-cache-dir
COPY . /app 
RUN cd /app && python manage.py migrate
CMD ["python", "/app/manage.py", "runserver", "localhost:8080"]
