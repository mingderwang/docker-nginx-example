FROM python:3.5-slim
RUN pip install gunicorn==19.9.0
COPY ./app/requirements.txt /tmp
RUN pip install -r /tmp/requirements.txt

COPY ./app/example.py /
EXPOSE 5000
WORKDIR /
ENTRYPOINT ["/usr/local/bin/gunicorn", "-b", ":5000", "example:app"]

