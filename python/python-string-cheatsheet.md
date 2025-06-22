# Python 文字列操作関数チートシート

## len  
文字列の長さを取得。空文字なら0。リスト等にも使える。

```python
text = "Hello"
length = len(text)
print(length)  # 出力: 5
```

## str  
任意のオブジェクトを文字列へ変換。UI表示やログ整形に便利。

```python
value = 123
text = str(value)
print(text)        # 出力: '123'
print(type(text))  # 出力: <class 'str'>
```

## format  
文字列内に値を埋め込む。テンプレートとして汎用性が高い。

```python
name = "Alice"
age = 30
msg = "名前は{}、年齢は{}です。".format(name, age)
print(msg)  # 出力: 名前はAlice、年齢は30です。
```

## replace  
文字列の中の一部を他の文字列に置換。全文や一部も可能。

```python
text = "apple banana apple"
result = text.replace("apple", "orange")
print(result)  # 出力: orange banana orange
```

## split  
区切り文字で文字列を分割し、リストにする。

```python
text = "apple,banana,cherry"
fruits = text.split(",")
print(fruits)  # 出力: ['apple', 'banana', 'cherry']
```

## join  
リストなどの要素を文字列で結合。CSV生成などに便利。

```python
fruits = ["apple", "banana", "cherry"]
result = ", ".join(fruits)
print(result)  # 出力: apple, banana, cherry
```

## strip  
前後の空白や改行を削除。中央の文字は影響なし。

```python
text = "  Hello World\n"
print(text.strip())  # 出力: 'Hello World'
```

## lstrip  
文字列の先頭から空白や指定文字を除去。

```python
text = "   Hello"
print(text.lstrip())  # 出力: 'Hello'
```

## rstrip  
文字列の末尾から空白や指定文字を除去。

```python
text = "Hello   "
print(text.rstrip())  # 出力: 'Hello'
```

## find  
指定文字列の最初の位置を返す。見つからない場合は -1。

```python
text = "apple banana apple"
print(text.find("banana"))  # 出力: 6
```

## rfind  
指定文字列の最後の位置を返す。見つからない場合は -1。

```python
text = "apple banana apple"
print(text.rfind("apple"))  # 出力: 13
```

## index  
findと同じだが、見つからないと例外（ValueError）を出す。

```python
text = "hello world"
print(text.index("world"))  # 出力: 6
```

## rindex  
rfindと同じだが、見つからないと例外（ValueError）を出す。

```python
text = "banana apple banana"
print(text.rindex("banana"))  # 出力: 13
```

## lower  
英字をすべて小文字に変換。

```python
text = "Python Programming"
print(text.lower())  # 出力: 'python programming'
```

## upper  
英字をすべて大文字に変換。

```python
text = "Python Programming"
print(text.upper())  # 出力: 'PYTHON PROGRAMMING'
```

## capitalize  
先頭文字を大文字、他を小文字に整形。

```python
text = "python programming"
print(text.capitalize())  # 出力: 'Python programming'
```

## title  
各単語の先頭を大文字にする。英文タイトル整形に便利。

```python
text = "python programming language"
print(text.title())  # 出力: 'Python Programming Language'
```

## startswith  
文字列が指定の接頭語で始まるかを確認。True/False を返す。

```python
url = "https://example.com"
print(url.startswith("https"))  # 出力: True
```

## endswith  
文字列が指定の接尾語で終わるかを確認。True/False を返す。

```python
filename = "report.pdf"
print(filename.endswith(".pdf"))  # 出力: True
```

## count  
部分文字列の出現回数を返す。存在しない場合は0。

```python
text = "banana"
print(text.count("a"))  # 出力: 3
```

## isdigit  
すべての文字が数字かをチェック。全角も対象。

```python
value = "12345"
print(value.isdigit())  # 出力: True
```

## isalpha  
すべての文字がアルファベットかを判定。

```python
name = "Alice"
print(name.isalpha())  # 出力: True
```

## isnumeric  
すべての文字が数値文字（漢数字・全角数字含む）か判定。

```python
value = "３２１"
print(value.isnumeric())  # 出力: True
```

## isalnum  
すべての文字が英数字かを判定。記号や空白は不可。

```python
token = "abc123"
print(token.isalnum())  # 出力: True
```

## isspace  
文字列がすべて空白文字（スペース、改行、タブ）かを判定。

```python
line = " \t\n"
print(line.isspace())  # 出力: True
```

## zfill  
指定桁数に満たない場合、左側をゼロ埋めで補完。

```python
num = "42"
print(num.zfill(5))  # 出力: '00042'
```

## encode  
文字列をエンコードしてバイト列に変換。

```python
text = "こんにちは"
binary = text.encode("utf-8")
print(binary)  # 出力: b'...'
```

## decode  
バイト列を指定エンコードで文字列に変換。

```python
binary = b'\\xe3\\x81\\x93\\xe3\\x82...'
text = binary.decode("utf-8")
print(text)  # 出力: 'こんにちは'
```
