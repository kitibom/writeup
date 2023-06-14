# Crack & Crack

> Just Crack & Crack! Author: NoobMaster

## 解法
unzipとpdf閲覧のためのパスワードをjohnで解析する

### unzip
```
$ zip2john flag.zip > hash.txt
$ john --wordlist=/var/workspace/list/rockyou.txt hash.txt
```
```
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
Will run 8 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
1337h4x0r        (flag.zip/flag.pdf)     
1g 0:00:00:02 DONE (2023-06-09 15:20) 0.3448g/s 4581Kp/s 4581Kc/s 4581KC/s 13744oga..13143604
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 
```
よって，以下でzipを解凍
```
$ unzip flag.zip -P 1337h4x0r
```

### pdf
```
$ /usr/share/john/pdf2john.pl flag.pdf > hash.txt 
$ john --wordlist=[パスワードファイルにはrockyou.txtを使用] hash.txt
```
```
Using default input encoding: UTF-8
Loaded 1 password hash (PDF [MD5 SHA2 RC4/AES 32/64])
Cost 1 (revision) is 4 for all loaded hashes
Will run 8 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
noobmaster       (flag.pdf)     
1g 0:00:01:26 DONE (2023-06-09 15:11) 0.01151g/s 57824p/s 57824c/s 57824C/s noobnoob1..noo0872344977
Use the "--show --format=PDF" options to display all of the cracked passwords reliably
Session completed. 
```

## flag
解凍したpdfに記載
> n00bz{CR4CK3D_4ND_CR4CK3D_1a4d2e5f}