# LeetCodeをTypeScriptでやるときのtips

随時更新して行く予定(2021/08/02時点)

## 文字列操作

### 文字列を一文字ずつにする

```typescript
'hello'.split('')
// [ 'h', 'e', 'l', 'l', 'o' ]
```

## 数値操作

### 符号を求める

```typescript
Math.sign(2)
// 1
Math.sign(-2)
// -1
Math.sign(0)
// 0
```

### 絶対値を求める

```typescript
Math.abs(-1)
// 1
Math.abs(1)
// 1
```

### 文字列 -> 数値変換

雑に変換したい場合はMath.parseIntを使う。

```typescript
parseInt("123")
// 123
parseInt("123-asdfalkdfja")
// 123
parseInt("-123")
// -123
```

### 数値の反転

```typescript
const num = 123;
Math.sign(num) * parseInt(String(num).split('').reverse().join(''))
// 321

const num2 = -123;
Math.sign(num2) * parseInt(String(num2).split('').reverse().join(''))
// -321
```

### 乗算

2^31とかわからなくなるので。

```typescript
> 2**31
// 2147483648
```

### 切り捨て?

厳密には引数に指定した整数値以下の最大整数を返す。負の値の場合は、最大整数が-9になるので切り捨てしまうと値が異なってしまう。

```typescript
Math.floor(9.2)
// 9
Math.floor(-9.2)
// -10
```

## 配列操作

### 重複削除

```typescript
const ary = [1,1,11,1,1,2,3,4,4,4,4,5];
const newArray = Array.from(new Set(ary));
// Set(6) { 1, 11, 2, 3, 4, 5 }
```
