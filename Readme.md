# guild2_codec

`guild2_codec.py` 是《The Guild 2 Renaissance》中文字体编码转换工具。

用于：

- 普通中文 → 游戏字体编码
- 游戏字体编码 → 普通中文
- 查询码位
- 查看编码表统计

## 依赖文件

```text
data\guild2_chinese_codec.json
```

该文件包含完整 codec 表：

- `plain_to_game`
- `plain_to_games`
- `game_to_plain`
- 游戏字体表中的全部 codepoint

当前覆盖：

```text
2984 个 codepoint
```

来源：

```text
Textures\Hud\chinese\Sets.dat
```

## 基本用法

### 编码

```bat
python guild2_codec.py encode "你好，法庭。"
python guild2_codec.py encode "你好，法庭。" --format entity
python guild2_codec.py encode "你好，法庭。" --format uplus
```

### 解码

```bat
python guild2_codec.py decode "ꆜꎳ겕꛳ꒊꄉ"
python guild2_codec.py decode "U+A19C U+A3B3 U+AC95 U+A6F3 U+A48A U+A109"
```

### 查询

```bat
python guild2_codec.py lookup "U+A19C U+AC91"
```

### 统计

```bat
python guild2_codec.py stats
```

## 支持的解码输入

```text
原始游戏字体字符
&#xA19C;
&#41372;
\uA19C
U+A19C
```

## 支持的输出格式

```text
raw
entity
decimal-entity
uplus
json
```

## 文件转换

### 编码文件

```bat
python guild2_codec.py encode --file input.txt --output output.txt --format raw --output-encoding utf-8
```

### 解码文件

```bat
python guild2_codec.py decode --file encoded.txt --output plain.txt
```

## 特殊项

以下两个码位会反向解码成多字符字符串：

```text
U+AC91 -> "% "
U+AC98 -> "/ "
```