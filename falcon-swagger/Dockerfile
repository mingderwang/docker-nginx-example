FROM python:3.5-slim
RUN pip install gunicorn==19.9.0
COPY ./app/requirements.txt /tmp
RUN pip install -r /tmp/requirements.txt

COPY ./app/hello_world_api.py /
EXPOSE 8000
WORKDIR /
ENTRYPOINT ["/usr/local/bin/gunicorn", "-b", ":8000", "hello_world_api:api"]

