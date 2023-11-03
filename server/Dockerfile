FROM nvcr.io/nvidia/tritonserver:23.05-pyt-python-py3

RUN pip install git+https://github.com/huggingface/transformers.git
RUN pip install protobuf==3.20.3 sentencepiece==0.1.99 accelerate==0.23.0 einops==0.6.1

COPY model-registry /model-registry

EXPOSE 8000 8001 8002
CMD ["tritonserver", "--model-repository=/model-registry", "--log-verbose=2"]
