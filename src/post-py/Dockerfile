FROM python:3.6.0-alpine

WORKDIR /app
ADD . /app

#RUN apk update && apk add  --no-cache python3-pip
RUN apk update && apk add  --no-cache gcc musl-dev && \
#  pip install --upgrade pip==19.0.3
  pip install -r /app/requirements.txt

ENV POST_DATABASE_HOST post_db
ENV POST_DATABASE posts

ENTRYPOINT ["python3", "post_app.py"]
