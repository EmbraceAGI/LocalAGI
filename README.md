# LocalAGI

基于 ChatGLM-6B 大模型的本地 AGI 实验。

本项目可实现全部使用**开源**模型**离线私有部署**。本项目中:

- ✅ LLM 默认选用 [ChatGLM-6B](https://github.com/THUDM/ChatGLM-6B), 可选 LLMDA。
- ✅ Embedding 默认选用 [GanymedeNil/text2vec-large-chinese](https://huggingface.co/GanymedeNil/text2vec-large-chinese/tree/main)
- ✅ Prompt 全部使用中文方便国内用户使用

## 用法

```
pip install -r requirements.txt
```

### ChatGLM API 部署

首先需要安装额外的依赖 `pip install fastapi uvicorn`，然后运行仓库中的 chatglm_server.py

```
python chatglm_server.py
```

默认部署在本地的 8001 端口，通过 POST 方法进行调用，正常响应则部署成功。

```
curl -X POST "http://127.0.0.1:8001" \
     -H 'Content-Type: application/json' \
     -d '{"prompt": "你好", "history": []}'
```

部署成功后不要关闭，让 ChatGLM API 服务在后台运行。

### 运行 LocalAGI

```
python local_agi.py
```

成功运行效果图：

![LocalAGI](imgs/LocalAGI_run1.jpg)


## 致谢

* [ChatGLM-6B](https://github.com/THUDM/ChatGLM-6B)
* [babyagi](https://github.com/yoheinakajima/babyagi)