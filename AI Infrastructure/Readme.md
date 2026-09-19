## AI Infrastructure Explained (GPUs, vLLM, and LLM-D)

![alt text](image.png)
![alt text](image-1.png)

![alt text](image-2.png)
    
    - cpu and ram sits in separate localtions
    - when we type 6*7 it 1st reach to RAM
    - Then it goes to CPU and the results are back to RAM
    - From RAM it displays the result.

 
### Challenges When we want to run the Model with CPU

    - Model calculatons are nothing but billions of multipleication parallel.
    - If we will do it CPU, we need to wait for vey long period as its doing sequntial operation.
    - So w eneed to use GPU to tackel the situation.

![alt text](image-3.png)

    - CPU manages 10 Trillion operations/sec
    - GPU manages 1000 Trillion Operations/sec
        GPU can work parallely

![alt text](image-4.png)
    
    - VRM Sits next to the GPU, kind of same board to data travel time is very minimal.
    - It will to TB per/sec transactions

![alt text](image-5.png)

![alt text](image-6.png)

### VLLM (Model Server)

![alt text](image-7.png)
![alt text](image-8.png)
![alt text](image-9.png)

![alt text](image-10.png)
![alt text](image-11.png)

    - 100 token output meaning the model is running again and again to produce the complete answer.

![alt text](image-13.png)
![alt text](image-12.png)

## What exactly happening inside the loop 

    - there are 2 phases
        - the pause (prefill)
        - the stream (Decode)
![alt text](image-14.png)

### Phase 1 (Pause / Prefill)
![alt text](image-15.png)

### Phase 2 (Streaming/ decode)

    - Writing a 200 token answer, you load the entire model out of memory 200 times over 
    - Each load gives kind of 1 token
![alt text](image-16.png)
![alt text](image-17.png)
![alt text](image-18.png)

## KV Cache

![alt text](image-19.png)

![alt text](image-20.png)

### Prefix Caching

![alt text](image-21.png)


Reference:-
- https://www.youtube.com/watch?v=hBzUokVYQkI
