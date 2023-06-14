# Secret Group

## 問題文
> Come and get the flag... Only if you can pass these impossible to pass conditions! Author: NoobMaster
>
> http://challs.n00bzunit3d.xyz:42552

## 解法
upper()により文字数が増える文字を探す
Unicode 0xfb03の`ﬃ`などが該当（uppser()すると3文字になる）
```
$ curl -L -X POST -d "username=ﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃ" http://challs.n00bzunit3d.xyz:42552/login
```

## flag
> n00bz{1mp0551bl3_c0nd1t10n5_m0r3_l1k3_p0551bl3_c0nd1t10ns}