# openssl
生成openssl包，用于快速生成自签名证书

1. 在用户目录生成生成私钥
```
docker run -v $PWD:/work -it ceil124/openssl openssl genrsa -out /work/server.key 1024
```

2. 使用私钥生成自签名的cert证书文件
```
docker run -v $PWD:/work -it ceil124/openssl \
openssl req -new -x509 -days 3650 -key /work/server.key -out /work/server.crt \
-subj "/C=CN/ST=mykey/L=mykey/O=mykey/OU=mykey/CN=domain1/CN=domain2/CN=domain3"
```
