# Chapter 5

## Type Matching

```haskell
-- 1. a => c.
not :: Bool -> Bool
-- 1. b => d.
length :: [a] -> Int
-- 1. c => b.
concat :: [[a]] -> [a]
-- 1. d => a.
head:: [a] -> a
-- 1. e => e.
(<) :: Ord a => a -> a -> Bool
--
```

## Type Arguments

```haskell
-- 1. a
f x :: Char -> Char -> Char
-- 2. d
g 0 'c' "woot" :: Char
-- 3. d
h 1.0 2 :: Num b => b
-- 4. c
h 1 (5.5 :: Double) :: Double
-- 5. a
jackal "keyboard" "has the word jackal in it" :: [Char]
-- 6. e
jackal "keyboard" :: Eq b => b -> [Char]
-- 7. d
kessel 1 2 :: (Num a, Ord a) => a
-- 8. a
kessel 1 (2 :: Integer) :: (Num a, Ord a) => a
-- 9. c
kessel (1 :: Integer) 2 :: Integer
```

## Parametricity

```haskell
-- 2.
f x y = x
g x y = y
-- 3.
h x y = y
```

## Apply Yourself

```haskell
-- 1.
myConcat :: [Char] -> [Char]
myConcat x = x ++ " yo"
-- 2.
myMult :: Fractional a => a -> a
myMult x = (x / 3) * 5
-- 3.
myTake :: Int -> [Char]
myTake x = take x "hey you"
-- 4.
myCom :: Int -> Bool
myCom x = x > (length [1..10])
-- 5.
myAlph :: Char -> Bool
myAlph x = x < 'z'
```

## Multiple choice

```haskell
-- 1. c
-- 2. a
-- 3. b
-- 4. c
```
