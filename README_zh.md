# guild2_codec

《行会2文艺复兴》的全局字体转码 CLI。

## 转码表

```text
..\data\guild2_codec.json
```

转码表是纯 JSON 字典。非 CJK 字符没进表时按 Unicode 原样通过。

```json
{"你":"ꆜ","ą":"ç"}
```

## 命令

```bat
python guild2_codec.py encode "你好，法庭。"
python guild2_codec.py decode "U+A19C U+A3B3 U+AC95 U+A6F3 U+A48A U+A109"
python guild2_codec.py lookup "你好"
python guild2_codec.py stats
```

## 文件

```bat
python guild2_codec.py encode --file input.txt --output output.txt
python guild2_codec.py decode --file encoded.txt --output plain.txt
```

## 缺失字符

```text
error     CJK/private 缺映射时报错
replace   使用 --replacement 替换
keep      保留原字符
drop      删除字符
```
