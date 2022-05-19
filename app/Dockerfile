#pull image
FROM python:3.9.6-alpine

#create directory and dedicated app user
RUN mkdir -p /home/appuser
RUN addgroup -S appuser && adduser -S appuser -G appuser

#change the working directory
WORKDIR /home/app

#update packages and install dependencies
RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev    
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

#change files ownership and switch to dedicated app user
RUN chown -R appuser:appuser /home/appuser
USER appuser

#copy app content into container
COPY . .