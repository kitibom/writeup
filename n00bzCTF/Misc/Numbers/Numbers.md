# Numbers

## 問題文
> Welcome to numbers! just answer my few questions to get the flag!
> - Note: To make this less confusing, I have an example. let's say if it asks - "How many 3's appear till 40?" The answer - 14 because ['3','13','23','30','31','32','33','33','34','35','36','37','38','39'].
> - Also, the '33' is counted twice (not a typo!) as the three occurs two times (once in the 'ones' digit place and once in the 'tens' digit place)(each entry in that list is like count++). Author: NoobMaster

## 解法
0とtillの扱いについてプログラムで試していると1以上指定された値以下で数えていることがわかる．

```
import socket

server_name = "challs.n00bzunit3d.xyz"
port_number = "13541"
bufsize = 4096


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as sock:
    sock.connect((server_name, int(port_number)))

    while True:
        rd = sock.recv(bufsize).decode()
        print(rd)
        if "n00bz" in rd:
            break
        num1 = rd.split("many ")[1].split("'s")[0]
        num2 = int(rd.split("till ")[1].split("?")[0])

        total = 0
        for i in range(1,num2):
            total += str(i).count(num1)
        
        print(total)
        sd = (str(total)+"\n").encode()
        sock.sendall(sd)
```

## flag
> n00bz{4n_345y_pr0gr4mm1ng_ch4ll}