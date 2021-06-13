FROM ubuntu:18.04

RUN mkdir data
RUN mkdir setupfiles
RUN mkdir notebooks
COPY requirements.txt /setupfiles/requirements.txt
ADD /notebooks /notebooks
RUN apt-get update && apt-get -y update 
RUN apt install -y python3 && apt install -y python3-pip && apt install -y git
RUN pip3 install -r /setupfiles/requirements.txt

RUN useradd -m app
WORKDIR /notebooks
CMD ["jupyter", "notebook", "--port=8888", "--no-browser", "--ip=0.0.0.0", "--allow-root"]