###### apns_test
根据自己的配置信息使用

/////////////

个人配置信息

cd apns_test/apnstest

php push.php


###### 获取证书步骤
1.对应生成不同证书，下载，双击；

2.在钥匙串中，将证书拖到登录下，此时导出才会提示p12文件；

3.需要通过终端命令将这些文件转换为PEM格式：

openssl pkcs12 -clcerts -nokeys -out apns-dev-cert.pem -in apns-dev-cert.p12

4.转换得到key的pem：

openssl pkcs12 -nocerts -out apns-dev-key.pem -in apns-dev-cert.p12

5.如果你想要移除密码，要么在导出/转换时不要设定或者执行：

openssl rsa -in apns-dev-key.pem -out apns-dev-key-noenc.pem

6.最后，你需要将键和许可文件合成为apns-dev.pem文件，此文件在连接到APNS时需要使用：

cat apns-dev-cert.pem apns-dev-key-noenc.pem > apns-dev.pem 

或者使用有密码的:

cat apns-dev-cert.pem apns-dev-key.pem > ck.pem

