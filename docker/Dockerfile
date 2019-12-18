FROM python:3.7-stretch

WORKDIR /app
RUN git clone https://github.com/YinAoXiong/12306_code_server.git
WORKDIR /app/12306_code_server

RUN pip3 install tensorflow==1.14.0 && \
    pip3 install -r requirements.txt

RUN wget -c https://github.com/YinAoXiong/12306_code_server/releases/download/v0.1-alpha/12306.image.model.h5 && \
    wget -c https://github.com/YinAoXiong/12306_code_server/releases/download/v0.1-alpha/model.v2.0.h5

EXPOSE 80

CMD ["gunicorn", "app:app", "-c", "gunicorn.conf.py"]
