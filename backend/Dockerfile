FROM python:3.10


RUN apt-get update && \
  apt-get install -y build-essential python3-dev && \
  curl https://sh.rustup.rs -sSf | sh -s -- -y && \
  apt-get clean

ENV PATH="/root/.cargo/bin:${PATH}"

RUN python3 -m pip install --upgrade pip

WORKDIR /usr/src/app
COPY requirements.txt ./

RUN pip install --no-cache-dir --upgrade -r ./requirements.txt
EXPOSE 3001

CMD [ "python", "./src/server.py" ]
