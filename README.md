# 正規表示式

[線上測試](https://regex101.com/)

[影片教學](https://www.youtube.com/watch?v=fmggOEPFW2c)

## Speical sequences

|   |special sequences|
|---|---              |
| \d| digit(0-9) |
| \D| Not a digit(0-9) |
| \w| word character(a-z, A-Z, 0-9,_) |
| \W| Not a word character |
| \s| whitespace (space, tab, blank line)|
| \S| Non-whitespace|
| \b| word boundary |
| \B| Not a word boundary |
| \A| Start of sting |
| \Z| End of string |


|   |special sequences|
|---|---              |
| \ | Escape special characters |
| . | Matches any character |
| $ | Matches end of string|
| ^ | Matches beginning of string |
| [] | Matches characters in brackets|
| [^]| Matches characters NOT in bracket|
| \| | Either or |
| () | Group |
| \A| Start of sting |
| \Z| End of string |

|   |special sequences|
|---|---              |
| * | 0 or more |
| + | 1 or more|
| ? | 0 or 1|
| {m} | Exactly m times |
| {n,} | Min n times|
| {m,n}| From m to n times|
| {m,n}? | From m to n, as few as possible|


## TEST

* `.` 不包含`\n`
```
\BHa # Ha前面不能是word boundary
\bHa\b # Ha前後都要是word boundary
(\d\d\d).\d\d\d.\d\d\d\d # ()會把它變成group
[6-9]\d\d.\d\d\d.\d\d\d\d # 找出6~9開頭的電話號碼
\d{3} # 找連續三個數字
6{4} # 剛好四個六
6{4,} # 至少四個六
\w{4,8} # 找至少4個，至多8個連續的字，越多越好
\w{3,5} # 找至少3個，至多5個連續的字，越少越好


First\.+Last # 至少1個.
(\w+)@(\w+)\.([a-z]+) # 信箱格式
```

## `{m,n}?`

* 在單純使用情況下與`{m}`相同
* 不過在`a{3,5}?b`，就會找出`aaab`,`aaaab`,`aaaaab`
* a{3}b，只會找出`aaab`
## replace

```
*@$2.$3 #把前面個人信箱給*掉，$2, $3代表第2,3個group，$python可能不能用
```