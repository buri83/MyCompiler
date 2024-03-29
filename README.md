# MyCompiler
コンパイラ（インタプリタも）を作りたいと思い、『コンパイラ：作りながら学ぶ』を読みながら遊んでみた、C++を使って記述。

# 実行方法
Makefileを実行して実行すると「test.src」が実行される。

```console
$ make
$ vi test.crc  # programming
$ ./a.out
```


# 記述
変数は整数型のみ、宣言は`var`を使用する。
なお、配列の宣言では整数値のみ使用可能。
```
  var temp, flag = 0, array[9];
  
  temp = 99;
  array[4] = 0;
```

関数の戻り値及び引数は整数型のみ。`def`で宣言する。
なお、コメントとして`#`が利用可能
```
def adder(x, y){
  return x + y;
}

var a = adder(4, 7);  # = 11
```

条件分岐と繰り返し処理は`if`及び`while`が使用可能。
整数の標準出力には`print`や`println`(改行有)を使う。
```
var a = 3, b = 2;
if(a + b == 3){
  println 1;
}else if(a * b == 6){
  println 0;
}else{
  print -1;
}

var i = 0;
while(i < 10){
  println i;
  i += 1;
}
```

使用できる演算、比較は以下をサポート

| 演算子 | 意味 |
|--------|-----|
| = += -= /= *= %= | 代入|
| && \|\| ! | 論理演算|
| & \| ^ ~ << >> | ビット演算|
| + - * / % | 演算|
| == != > >= < <= | 比較 |

LL法での構文解析を行い、複雑な計算も可能
```
a = i * (6 + 2 / 6 << (1 + 3)) % f(6, 3);
```

# stackmachine
`stackmachine_gram.md`を参照

# 参考
- コンパイラ作りながら学ぶ
