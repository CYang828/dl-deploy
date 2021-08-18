# 快速开始


1. 克隆本项目

```bash
git clone https://github.com/BSlience/dl-deploy.git
```

2. 安装依赖包

```bash
pip install -r requirements.txt
```

3. 下载部署中使用的模型，并确保放在 assets 目录下

```bash
wget http://aimaksen.bslience.cn/torch-bert-sentiment.bin -P assets/
```

4. 启动服务

```bash 
uvicorn sentiment_analyzer.api:app
```


5. 测试服务

先安装 [HTTPie](https://httpie.io/)，然后运行下面命令

```bash
# other console
http POST http://localhost:8000/predict text="OMG. I love how easy it is to stick to my schedule. Would recommend to everyone"
```

```json
{
    "confidence": 0.9999295473098755,
    "probabilities": {
        "negative": 1.7753758584149182e-05,
        "neutral": 5.275019793771207e-05,
        "positive": 0.9999295473098755
    },
    "sentiment": "positive"
}
```