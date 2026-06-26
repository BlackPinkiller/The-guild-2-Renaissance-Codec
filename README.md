# guild2_codec

Global font codec CLI for The Guild 2 Renaissance.

## Codec Table

```text
..\data\guild2_codec.json
```

The table is a plain JSON dictionary. Unlisted non-CJK characters pass through as Unicode.

```json
{"你":"ꆜ","ą":"ç"}
```

## Commands

```bat
python guild2_codec.py encode "你好，法庭。"
python guild2_codec.py decode "U+A19C U+A3B3 U+AC95 U+A6F3 U+A48A U+A109"
python guild2_codec.py lookup "你好"
python guild2_codec.py stats
```

## Files

```bat
python guild2_codec.py encode --file input.txt --output output.txt
python guild2_codec.py decode --file encoded.txt --output plain.txt
```

## Missing Characters

```text
error     fail on missing CJK/private characters
replace   use --replacement
keep      keep original character
drop      remove character
```
