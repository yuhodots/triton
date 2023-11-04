# Triton

## An Example for Python BackEnd

You can start triton server and client containers simutaneouly with docker-compose

``` shell
docker compose up
```

You can pass a request with interactive mode after attaching the client container.

``` shell
curl -X POST tritonserver:8000/v2/models/falcon7b/infer -d '{"inputs": [{"name":"text_input","datatype":"BYTES","shape":[1],"data":["How can you be"]}]}'
```

Then you can get a response from triton server!

```
{
    "model_name": "falcon7b",
    "model_version": "1",
    "outputs": [
            {
                "name": "text_output",
                "datatype": "BYTES",
                "shape": [1],
                "data": ["How can you be sure that you are getting the best deal on your car"]
            }
        ]
    }
```

If you want to pass a request without creat a client container, plase add `network_mode: host` in docker-compose.yaml.


## PyTorch BackEnd

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

## Warning

You **should not have empty directories** in your Triton model repository.

Refer this issue: https://github.com/triton-inference-server/server/issues/5786#issuecomment-1626340702


## Reference

- [triton-inference-server/tutorials](https://github.com/triton-inference-server/tutorials/tree/main/Quick_Deploy/HuggingFaceTransformers)

