FROM nvcr.io/nvidia/tritonserver:23.09-py3

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    curl

RUN pip install transformers==4.34.0 protobuf==3.20.3 sentencepiece==0.1.99 accelerate==0.23.0 einops==0.6.1

EXPOSE 8000 8001 8002
CMD ["tritonserver", "--model-repository=/model-registry", "--log-verbose=2"]
