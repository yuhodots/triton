FROM python:3.8

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    curl

RUN python3 -m pip install -U pip && \
    python3 -m pip install -U setuptools

CMD ["curl", "-X", "POST", "tritonserver:8000/v2/models/falcon7b/infer", "-d", \
     "{\"inputs\": [{\"name\":\"text_input\",\"datatype\":\"BYTES\",\"shape\":[1],\"data\":[\"I am going\"]}]}"]
