# george-kirillov_infra
george-kirillov Infra repository

## Cпособ подключения к someinternalhost в одну команду

``` bash
ssh -i ~/.ssh/appuser -J appuser@62.84.125.38 appuser@10.129.0.14
```

## вариант решения для подключения из консоли при помощи команды вида ssh someinternalhost

``` bash
cat <<EOF> ~/.ssh/config
Host someinternalhost
 HostName 10.129.0.14
 User appuser
 ProxyJump appuser@62.84.125.38
 IdentityFIle ~/.ssh/appuser
EOF
```
