# Triton

## Python BackEnd Example

You can start triton server and client containers simutaneouly with docker-compose

``` shell
docker compose up
```

Then you can check a response in the client container for default input: 

`{"inputs": [{"name":"text_input","datatype":"BYTES","shape":[1],"data":["I am going"]}]}`

```
"I am going to be in the market for a new laptop soon. I"
```

You can pass another request with interactive mode after attaching the client container.

``` shell
curl -X POST localhost:8000/v2/models/falcon7b/infer -d '{"inputs": [{"name":"text_input","datatype":"BYTES","shape":[1],"data":["How can you be"]}]}'
```

## Pytorch BackEnd

If you want to deploy your own model with Pytorch BackEnd, refer this architecture.

```
model-registry
|
+-- <model_name>
    |
    +-- config.pbtxt
    +-- 1
        |
        +-- model.pt
```

## Reference

- [triton-inference-server/tutorials](https://github.com/triton-inference-server/tutorials/tree/main/Quick_Deploy/HuggingFaceTransformers)
