# nkf library
nkf can convert ASCII, S-JIS to UTF-8.

## Install nkf
```bash
$ sudo pat install -y nkf
```

## Check type of charcter mode
```bash
$ ngf -g hoge.html
```

## Convert to ukf-8
```bash
$ nkf -w --overwrite hoge.html
```

## Other option(Japanease)
- `-u` 出力時にバッファリングを行わない
- `-j` JISコードに変換する
- `-e` EUCコードに変換する
- `-s` シフトJISコードに変換する
- `-w` UTF8コードに変換する
- `-r` ROT13/47の変換する
- `-T` テキスト・モードで出力する
- `file` 変換元のファイルを指定する
- `-g` 文字コード自動判別の結果を表示
- `–overwrite` 引数のファイルに直接上書き

### References
- http://kawatama.net/others/mac/1754
