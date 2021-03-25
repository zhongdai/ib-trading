FROM python:3.7-slim
# required to build grpcio (dependency of google-cloud-xxx pip packages)
RUN apt-get update -y && apt-get install -y build-essential gcc musl-dev

WORKDIR /usr/src/app

RUN pip install --upgrade pip
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY ./ibapi/* ./ibapi/
COPY allocator.py ./

CMD [ "python", "./allocator.py" ]
