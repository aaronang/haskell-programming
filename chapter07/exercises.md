# Chapter 7

## Grab Bag

```haskell
-- 1. a ≡ d
-- 2. d
-- 3. a.
addOneIfOdd n = case odd n of
  True -> f n
  False -> n
  where f = \n -> n + 1
-- 3. b.
addFive = \x -> \y -> (if x > y then y else x) + 5
-- 3. c.
mflip f x y = f x y
```

## Variety Pack

```haskell
-- 1. a.
k :: (a, b) -> a
-- 1. b. Not the same type as k1 or k3.
k2 :: String
-- 1. c. k3.
f :: (a, b, c) -> (d, e, f) -> ((a, d), (c, f))
f (a, b, c) (d, e, f) = ((a, d), (c, f))
```

## Case Practice

```haskell
-- 1.
functionC x y =
  case x > y of
    True  -> x
    False -> y
-- 2.
ifEvenAdd2 n =
  case even n of
    True  -> n + 2
    False -> n
-- 3.
nums x =
  case compare x 0 of
    LT -> -1
    GT -> 1
    EQ -> 0
```

## Artful Dodgy

```haskell
dodgy :: Num a => a -> a -> a
dodgy x y = x + y * 10
oneIsOne :: Num a => a -> a
oneIsOne = dodgy 1
oneIsTwo :: Num a => a -> a
oneIsTwo = (flip dodgy) 2
-- 1.
Prelude> dodgy 1 0
1
-- 2.
Prelude> dodgy 1 1
11
-- 3.
Prelude> dodgy 2 2
22
-- 4.
Prelude> dodgy 1 2
21
-- 5.
Prelude> dodgy 2 1
12
-- 6.
Prelude> oneIsOne 1
11
-- 7.
Prelude> oneIsOne 2
21
-- 8.
Prelude> oneIsTwo 1
21
-- 9.
Prelude> oneIsTwo 2
22
-- 10.
Prelude> oneIsOne 3
31
-- 11.
Prelude> oneIsTwo 3
23
```

## Guard Duty

```haskell
-- 3. b.
-- 4. Any list.
-- 5.
pal :: Eq a => [a] -> Bool
-- 6. c.
-- 7. Any instance of the Num class.
-- 8.
numbers :: (Eq a, Num a, Num b) => a -> b
```
