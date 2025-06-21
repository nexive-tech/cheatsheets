# PHP 配列操作関数チートシート

## array_merge
複数の配列を結合。数値キーは再付番、文字列キーは後勝ち。

```php
$array1 = ["a" => 1, "b" => 2];
$array2 = ["b" => 3, "c" => 4];
$result = array_merge($array1, $array2);
// ["a" => 1, "b" => 3, "c" => 4]
```

## array_push
配列の末尾に1つ以上の要素を追加。

```php
$stack = [1, 2];
array_push($stack, 3, 4);
// [1, 2, 3, 4]
```

## array_pop
配列の末尾の要素を取り出して削除。

```php
$stack = [1, 2, 3];
$last = array_pop($stack);
// $last = 3, $stack = [1, 2]
```

## array_shift
配列の先頭の要素を取り出して削除。

```php
$queue = [1, 2, 3];
$first = array_shift($queue);
// $first = 1, $queue = [2, 3]
```

## array_unshift
配列の先頭に1つ以上の要素を追加。

```php
$queue = [2, 3];
array_unshift($queue, 1);
// [1, 2, 3]
```

## array_slice
配列の一部を抜き出して新しい配列に（非破壊）。

```php
$input = ["a", "b", "c", "d"];
$output = array_slice($input, 1, 2);
// ["b", "c"]
```

## array_splice
配列の一部を削除し、置換や挿入を行う（破壊的）。

```php
$input = ["red", "green", "blue"];
array_splice($input, 1, 1, ["yellow", "purple"]);
// ["red", "yellow", "purple", "blue"]
```

## array_keys
配列のキーを取得。

```php
$data = ["a" => 1, "b" => 2, "c" => 1];
array_keys($data, 1);
// ["a", "c"]
```

## array_values
配列の値のみを取得。

```php
$data = ["a" => 100, "b" => 200];
array_values($data);
// [100, 200]
```

## array_map
各要素に関数を適用。

```php
$numbers = [1, 2, 3];
$squared = array_map(fn($n) => $n * $n, $numbers);
// [1, 4, 9]
```

## array_filter
条件に合う要素だけを抽出。

```php
$numbers = [1, 2, 3, 4];
$even = array_filter($numbers, fn($n) => $n % 2 === 0);
// [1 => 2, 3 => 4]
```

## array_reduce
配列を順に処理して1つの値に集約。

```php
$numbers = [1, 2, 3, 4];
$sum = array_reduce($numbers, fn($carry, $item) => $carry + $item, 0);
// 10
```

## in_array
値が配列に存在するか確認。

```php
$colors = ["red", "green", "blue"];
in_array("green", $colors);
// true
```

## array_search
指定値のキーを取得。

```php
$fruits = ["a" => "apple", "b" => "banana"];
$key = array_search("banana", $fruits);
// "b"
```

## array_key_exists
キーの存在を確認。

```php
$data = ["name" => "Taro", "age" => 20];
array_key_exists("age", $data);
// true
```

## count
配列の要素数を取得。

```php
$items = ["apple", "banana", "orange"];
count($items);
// 3
```

## sort
値を昇順に並び替え（キー再付番）。

```php
$numbers = [3, 1, 2];
sort($numbers);
// [1, 2, 3]
```

## rsort
値を降順に並び替え（キー再付番）。

```php
$numbers = [3, 1, 2];
rsort($numbers);
// [3, 2, 1]
```

## asort
値を昇順に並び替え（キー保持）。

```php
$data = ["a" => 3, "b" => 1, "c" => 2];
asort($data);
// ["b" => 1, "c" => 2, "a" => 3]
```

## arsort
値を降順に並び替え（キー保持）。

```php
$data = ["a" => 3, "b" => 1, "c" => 2];
arsort($data);
// ["a" => 3, "c" => 2, "b" => 1]
```

## ksort
キーを昇順に並び替え。

```php
$data = ["b" => 2, "a" => 1, "c" => 3];
ksort($data);
// ["a" => 1, "b" => 2, "c" => 3]
```

## krsort
キーを降順に並び替え。

```php
$data = ["a" => 1, "b" => 2, "c" => 3];
krsort($data);
// ["c" => 3, "b" => 2, "a" => 1]
```

## shuffle
配列をランダムに並び替え。

```php
$deck = [1, 2, 3, 4, 5];
shuffle($deck);
// ランダム順
```

## array_unique
重複する値を除去。

```php
$nums = [1, 2, 2, 3];
array_unique($nums);
// [0 => 1, 1 => 2, 3 => 3]
```

## array_diff
差集合（他に含まれない要素）を取得。

```php
$a = [1, 2, 3];
$b = [2, 4];
array_diff($a, $b);
// [0 => 1, 2 => 3]
```

## array_intersect
共通部分（積集合）を取得。

```php
$a = [1, 2, 3];
$b = [2, 3, 4];
array_intersect($a, $b);
// [1 => 2, 2 => 3]
```
