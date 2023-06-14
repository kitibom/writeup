# QRazy CSV

## 問題文
> A csv file contains a hidden surprise that will lead you to the next level. But it’s not easy to find. Can you uncover it and solve it? Author: noob_abhinav

## 解法
問題タイトルとCSV内容からQRコードの黒部分がrow,colで表記されていると推測し，以下のVBAを実行
```
Sub colorblack()
    Dim i
    Dim r
    Dim c
    
    For i = 2 To 428
        r = Cells(i, 1).Value
        c = Cells(i, 2).Value
        Cells(r + 2, c + 5).Interior.Color = RGB(0, 0, 0)
    Next i
End Sub
```
行列情報は区切り文字分割し，行：A列1行目～，列：B列1行目～それぞれ情報を格納している

出てきたQRコードを以下のサイトで読み取る

## flag
> n00bz{qr_c0d3_1n_4_t3xt_f1l3_w0w!!!!!!}