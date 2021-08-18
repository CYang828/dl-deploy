# Quick Start


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

```bash
# other console
http POST http://localhost:8000/predict text="OMG. I love how easy it is to stick to my schedule. Would recommend to everyone"```
```json
{
    "confidence": 0.999885082244873,
    "probabilities": {
        "negative": 0.999885082244873,
        "neutral": 8.876612992025912e-05,
        "positive": 2.614063305372838e-05
    },
    "sentiment": "negative"
}
```