# george-kirillov_infra
george-kirillov Infra repository

## Cпособ подключения к someinternalhost в одну команду

``` bash
ssh -i ~/.ssh/appuser -J appuser@84.201.133.46 appuser@10.129.0.14
```

## вариант решения для подключения из консоли при помощи команды вида ssh someinternalhost

``` bash
cat <<EOF> ~/.ssh/config
Host someinternalhost
 HostName 10.129.0.14
 User appuser
 ProxyJump appuser@84.201.133.46
 IdentityFIle ~/.ssh/appuser
EOF
```

bastion_IP = 84.201.133.46
someinternalhost_IP = 10.129.0.14
