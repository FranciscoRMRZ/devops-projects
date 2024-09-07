FROM python:3.12.5-alpine3.20

WORKDIR /flask-app

COPY ./src/requirements.txt ./requirements.txt

RUN pip install --upgrade pip
RUN pip install -r ./requirements.txt

COPY ./src .

CMD [ "python3", "-m", "flask", "run", "--host=0.0.0.0" ]
