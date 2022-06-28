# RedisAI-demo

## Examples
 - 1. serving-by-fastapi
 - 2. redis-cluster-by-docker-compose
<br>

## Ex 1. serving-by-fastapi
### Setup
1. Git clone 
```bash
git clone https://github.com/jaehyeongAN/RedisAI-demo.git
```

2. Move to dir
```bash
cd RedisAI-demo/serving-by-fastapi
```

3. Install Dependencies
```bash
pip install -r requirements.txt
```

4. Run FastAPI server
```bash
uvicorn main:app 
```
<br>

### Endpoint 
1. <code>/train</code>
 - 1. Load iris dataset.
 - 2. Train model using LogisticRegression of sklearn.
 - 3. Conver sklearn model to ONNX model.
 - 4. Save ONNX model to RedisAI
```bash
http GET localhost:8000/train
```

2. <code>/inference</code>
 - 1. Check Model 
 - 2. Set input tensor to RedisAI
 - 3. Model execute
 - 4. Get result
```bash
http GET "localhost:8000/inference?model=iris-clf&sepal_length=4.7&sepal_width=3.2&petal_length=1.6&petal_width=0.2"
```
![](./tmp/inference-fastapi.png)

<br>

## Ex 2. redis-cluster-by-docker-compose
...