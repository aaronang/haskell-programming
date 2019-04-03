# Chapter 9

## EnumFromTo

```haskell
eftBool :: Bool -> Bool -> [Bool]
eftBool x y
  | x > y     = []
  | x == y    = [x]
  | otherwise = x : (eftBool (succ x) y)

eftOrd :: Ordering -> Ordering -> [Ordering]
eftOrd x y
  | x > y     = []
  | x == y    = [x]
  | otherwise = x : (eftOrd (succ x) y)

eftInt :: Int -> Int -> [Int]
eftInt x y
  | x > y     = []
  | x == y    = [x]
  | otherwise = x : (eftInt (succ x) y)

eftChar :: Char -> Char -> [Char]
eftChar x y
  | x > y     = []
  | x == y    = [x]
  | otherwise = x : (eftChar (succ x) y)
```

## Thy Fearful Symmetry

```haskell
-- 1.
myWords :: String -> [String]
myWords [] = []
myWords x  = takeWhile (/=' ') x : (myWords $ dropWhile (==' ') $ dropWhile (/=' ') x)
-- 2.
myLines :: String -> [String]
myLines [] = []
myLines x  = takeWhile (/='\n') x : (myLines $ dropWhile (=='\n') $ dropWhile (/='\n') x)
-- 3.
split :: Char -> String -> [String]
split _ [] = []
split d x  = takeWhile (/=d) x : (split d $ dropWhile (==d) $ dropWhile (/=d) x)
myWords = split ' '
myLines = split '\n'
```

## Bottom Madness

```haskell
-- Will it blow up?
-- 1. ⊥
-- 2. [1]
-- 3. ⊥
-- 4. 3
-- 5. ⊥
-- 6. [2]
-- 7. ⊥
-- 8. [1]
-- 9. [1, 3]
-- 10. ⊥

-- Intermission: Is it in normal form?
-- 1. normal form
-- 2. weak head normal form
-- 3. neither
-- 4. neither
-- 5. neither
-- 6. neither
-- 7. weak head normal form
```

## More Bottoms

```haskell
-- 1. ⊥
-- 2. [1]
-- 3. ⊥
-- 4. Returns for each character whether it is a vowel.
itIsMystery :: String -> [Bool]
-- 5. a.
Prelude> map (^2) [1..10]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
-- 5. b.
Prelude> map minimum [[1..10], [10..20], [20..30]]
[1, 10, 20]
-- 5. c.
Prelude> map sum [[1..5], [1..5], [1..5]]
[15, 15, 15]
```

## Filtering

```haskell
-- 1.
filter (\x -> rem x 3 == 0) [1..30]
-- 2.
length . filter (\x -> rem x 3 == 0)
-- 3.
filter (\x -> not $ elem x ["the", "a", "an"]) . words
```

## Zipping

```haskell
-- 1.
zip [] _ = []
zip _ [] = []
zip (x:xs) (y:ys) = (x, y) : zip xs ys
-- 2.
zipWidth f [] _ = []
zipWidth f _ [] = []
zipWidth f (x:xs) (y:ys) = (f x y) : zipWidth f xs ys
-- 3.
zip = zipWidth (\x y -> (x, y))
```
