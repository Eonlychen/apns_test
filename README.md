###### apns_test
根据自己的配置信息使用

/////////////

个人配置信息

cd apns_test/apnstest

php push.php


###### 获取证书步骤
1.对应生成不同证书，下载，双击；

2.在钥匙串中，将证书拖到登录下，此时导出才会提示p12文件（设定好密码，下面要用）；

3.需要通过终端命令将cer,p12文件转换为PEM格式：

openssl x509 -in apns_dev.cer -inform der -out apns_dev.pem
openssl pkcs12 -nocerts -out fromkey.pem -in apns_key.p12

4.将两个pem文件合成一个最终文件，苹果服务器用

cat fromcer.pem fromkey.pem > final.pem

5.执行命令

php push.php
