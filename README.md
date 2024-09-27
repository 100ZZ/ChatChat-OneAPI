### Docker-Compose部署方式
>- git clone https://github.com/100ZZ/Chatchat-OneAPI.git
>- cd Chatchat-OneAPI
>- docker-compose up -d

### OneAPI配置修改
添加渠道，api-key，新建一个令牌

### Chatchat配置修改
坑爹的找了半天，模型配置，还要进容器去init一把，才能生成yml文件

>- docker exec -it chatchat /bin/sh
>- cd /root/chatchat_data
>- chatchat init

最终配置文件就可以映射过来：

>- ls chatchat
>- data  
>- basic_settings.yaml (知识库存储路径：KB_ROOT_PATH，DB_ROOT_PATH，SQLALCHEMY_DATABASE_URI)
>- kb_settings.yaml (默认FAISS)
>- model_settings.yaml (模型配置：DEFAULT_LLM_MODEL，DEFAULT_EMBEDDING_MODEL，修改OneAPI的key和模型)
>- prompt_settings.yaml 
>- tool_settings.yaml

### 重启服务
>- docker-compose restart

访问地址：http://localhost:8501

