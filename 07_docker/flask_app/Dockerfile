FROM python:3.12.5-alpine3.20

ENV MESSAGE="Hello from Docker!"

WORKDIR /flask-app

COPY ./src/requirements.txt ./requirements.txt

RUN pip install --upgrade pip
RUN pip install -r ./requirements.txt

COPY ./src .

# HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 CMD [ "executable" ]
HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD ["curl", "-f", "http://localhost:5000/", "||", "exit", "1"]

CMD [ "python3", "-m", "flask", "run", "--host=0.0.0.0" ]
