FROM python:3.8-alpine

COPY repositories /etc/apk/repositories

RUN	apk update && \
	apk --no-cache --update add build-base \
	libffi-dev \
	openssl-dev && \
	python3 -m pip install funcx jupyter -i https://mirrors.aliyun.com/pypi/simple/

WORKDIR /root/work/
EXPOSE 8888
CMD ["jupyter", "notebook", "--allow-root", "--ip=0.0.0.0", "--port=8888", "--NotebookApp.token=123456"]
