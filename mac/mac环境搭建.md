##### mongoDB

1. 解压后将解压的文件夹移动到/usr/local下面

2. 首先我们在根目录下创建data/db目录$ sudo mkdir -p /data/db

3. 给 /data/db设置读写权限 sudo chown username /data/db

4. 设置环境变量  vi ~/.bash_profile PATH=$PATH:/usr/local/mongoDB/bin5. source ~/.bash_profile

 

##### python

mac更改默认python 

```alias python="/jason/Library/Frameworks/Python.framework/Versions/3.9/bin/python3.9"```

