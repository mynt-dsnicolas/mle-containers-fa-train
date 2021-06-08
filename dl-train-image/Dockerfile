FROM fastdotai/fastai
USER root
RUN apt-get update && apt-get -y upgrade
RUN useradd --create-home train
WORKDIR /home/train
USER train
RUN mkdir /home/train/requirements
WORKDIR /home/train/requirements
COPY requirements.txt .
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
COPY opt/ /home/train/opt/
WORKDIR /home/train/opt/dl/code
ENTRYPOINT ["python3"]
CMD ["train"]