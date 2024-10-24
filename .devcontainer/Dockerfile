FROM zklcdc/go-proxy-bingai:latest-with-pass

USER root

RUN apt-get update && apt-get install wget curl -y

RUN wget https://github.com/Harry-zklcdc/go-proxy-bingai/releases/download/nightly/go-proxy-bingai-linux-amd64.tar.gz -O go-proxy-bingai-linux-amd64.tar.gz && \
    tar -zxvf go-proxy-bingai-linux-amd64.tar.gz && \
    chmod +x go-proxy-bingai

RUN wget https://github.com/Harry-zklcdc/go-bingai-pass/releases/latest/download/go-bingai-pass-linux-amd64.tar.gz -O go-bingai-pass-linux-amd64.tar.gz && \
    tar -zxvf go-bingai-pass-linux-amd64.tar.gz && \
    chmod +x go-bingai-pass

RUN rm go-bingai-pass-linux-amd64.tar.gz go-proxy-bingai-linux-amd64.tar.gz

USER $GBP_USER

COPY supervisor.conf /etc/supervisor/conf.d/supervisor.conf

EXPOSE 8080 45678 9005

CMD [ "/usr/bin/bash", "-c", "while true;do sleep 3600;done" ]