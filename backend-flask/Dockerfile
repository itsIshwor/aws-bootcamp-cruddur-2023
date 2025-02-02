FROM python:3.10-slim-buster

WORKDIR /backend-flask
COPY requirements.txt requirements.txt

COPY . .

RUN pip3 install -r requirements.txt
ENV FLASK_ENV=devlopment

EXPOSE ${PORT}

CMD [ "python", "-m", "flask", "run", "--host=0.0.0.0", "--port=4567" ]
