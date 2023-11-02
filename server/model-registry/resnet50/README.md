
1. Train model
2. Export model as a JIT
3. Refer to the architecture below and Put a JIT model named `model.pt`
4. Run tritonserver and Pass a request in a client container

```
model-registry
|
+-- resnet50
    |
    +-- config.pbtxt
    +-- 1
        |
        +-- model.pt
```
