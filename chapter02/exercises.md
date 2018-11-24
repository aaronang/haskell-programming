# Chapter 2

## Comprehension Check

```haskell
-- 1.
let half x = x / 2
let square x = x * x

-- 2.
f x = 3.14 * x * x

-- 3.
f x = pi * x * x
```

## Parentheses and Association

```haskell
-- 1. Not alike.
-- 2. Alike.
-- 3. Not alike.
```

## Heal the Sick

```haskell
-- 1.
let area x = 3.14 * x * x

-- 2.
let double x = x * 2

-- 3.
x = 7
y = 10
f = x + y
```

## A Head Code

```haskell
-- 1. 5
let x = 5 in x

-- 2. 25
let x = 5 in x * x

-- 3. 30
let x = 5; y = 6 in x * y

-- 4. 6
let x = 3; y = 1000 in x + 3
```

```haskell
-- 1.
a = x * 3 + y
  where x = 3
        y = 1000

-- 2.
b = x * 5
  where y = 10
        x = 10 * 5 + y

-- 3.
c = z / x + y
  where x = 7
        y = negate x
        z = y * 10
```

## Parenthesization

```haskell
-- 1.
2 + (2 * 3) - 1

-- 2.
(^) 10 $ (1 + 1)

--3.
(2 ^ 2) * (4 ^ 5) + 1
```

## Equivalent expressions

```haskell
-- 1. Same.
-- 2. Same.
-- 3. Different.
-- 4. Different.
-- 5. Different.
```

## More fun with functions

```haskell
*Main> let z = 7
*Main> let y = z + 8
*Main> let x = y ^ 2
*Main> let waxOn = x * 5

-- 1.
*Main> 10 + waxOn
1135
*Main> (+10) waxOn
1135
*Main> (-) 15 waxOn
-1110
*Main> (-) waxOn 15
1110

-- 2.
*Main> let triple x = x * 3

-- 3.
*Main> triple waxOn
3375

--4.
waxOn = x * 5
  where
    z = 7
    y = z + 8
    x = y ^ 2
```
