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
