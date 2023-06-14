# Secret Group

## 問題文
> To get the flag, you must be a member of the secret group! Author: NoobMaster
>
> http://challs.n00bzunit3d.xyz:31401/

## 解法
指定されるHTTPヘッダを変えてGETリクエストを投げる
```
$ curl -L -A "n00bz-4dm1n" -H "Accept:fl4g" -H "Connection:s3cur3" -H "referer:s3cr3t.n00bz-4dm1n.xyz" -H "Give-Flag:7ru3" http://challs.n00bzunit3d.xyz:31401/
```

## flag
> n00bz{y0u_4r3_n0w_4_v4l1d_m3mb3r_0f_th3_s3cr3t_gr0up!}