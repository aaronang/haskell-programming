# Chapter 4

## Mood Swing

```haskell
data Mood = Blah | Woot deriving Show
-- 1. `Mood`.
-- 2. `Blah` or `Woot`.
-- 3. `Woot` is a value and not a datatype.
-- 4.
changeMood :: Mood -> Mood
changeMood Blah = Woot
changeMood _Woot_ = Blah
```

## Find the Mistakes

```haskell
-- 1.
not True && True
-- 2.
not (x == 6)
-- 3. No mistakes.
-- 4.
["Merry"] > ["Happy"]
-- 5. Operands need to have identical types.
```

## Awesome

```haskell
awesome = ["Papuchon", "curry", ":)"]
also = ["Quake", "The Simons"]
allAwesome = [awesome, also]
-- 1.
length :: [a] -> Int
-- 2.
Prelude> length [1, 2, 3, 4, 5]
5
Prelude> length [(1, 2), (2, 3), (3, 4)]
3
Prelude> length allAwesome
2
Prelude> length (concat allAwesome)
5
-- 3. The latter doesn't work.
-- 4.
6 `div` length [1, 2, 3]
-- 5. Bool.
-- 6. False :: Bool.
-- 7.
Prelude> length allAwesome == 2
True
Prelude> length [1, 'a', 3, 'b'] -- Should error.
Prelude> length allAwesome + length awesome
5
Prelude> (8 == 8) && ('b' < 'a')
False
Prelude> (8 == 8) && 9 -- Should error.
-- 8.
isPalindrome :: (Eq a) => [a] -> Bool
isPalindrome x = x == reverse x
-- 9.
myAbs :: Integer -> Integer
myAbs x = if x < 0 then (-x) else x
-- 10.
f :: (a, b) -> (c, d) -> ((b, d), (a, c))
f x y = ((b, d), (a, c))
  where
    a = fst x
    b = snd x
    c = fst y
    d = snd y
```

## Correcting syntax

```haskell
-- 1.
x = (+)
f xs = w `x` 1
  where w = length xs
-- 2.
id x = x
-- 3.
f (a, b) = a
```

## Match the function names to their types

```haskell
-- 1. c.
-- 2. b.
-- 3. a.
-- 4. d.
```
