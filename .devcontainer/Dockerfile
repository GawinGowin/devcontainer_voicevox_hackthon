FROM node:19

WORKDIR /home

RUN npm install -g serve

RUN apt-get update && apt-get upgrade -y && apt-get install -y --no-install-recommends git
RUN git clone https://github.com/yusei53/voicevox_hackthon

RUN apt-get install -y --no-install-recommends \
    python3 python3-pip python3-dev libasound2-dev

#RUN apt-get install -y --no-install-recommends \
#    libglib2.0-0 libsm6 libxrender1 libxext6 libgl1-mesa-dev libcurl4-openssl-dev

COPY ./requirements.txt ./
RUN pip3 install --no-cache-dir install --upgrade pip
RUN pip3 --disable-pip-version-check --no-cache-dir install --user -r ./requirements.txt
RUN rm ./requirements.txt

ENTRYPOINT tail -f /dev/null