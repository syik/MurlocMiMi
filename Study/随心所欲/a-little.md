### Dockerfile Cache 小知识
 因为 Dockerfile 会把每一行生成一个 Intermediate Image 作为缓存，如果没有改变则使用Cache，减少编译时间。
```
COPY . /src/
RUN pip install --requirement /src/requirements.txt
```
变更为
```
COPY requirements.txt /src/
RUN pip install --requirement /src/requirements.txt
COPY . /src/
```



