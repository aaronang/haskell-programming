# Chapter 3

## Scope

```haskell
-- 1. Yes.
-- 2. No.
-- 3. No.
-- 4. Yes.
```

## Syntax Error

```haskell
-- 1.
(++) [1,2,3] [4,5,6]

-- 2.
"<3" ++ " Haskell"

-- 3. No syntax errors.
```

## Reading syntax

```haskell
-- 1. a. Correct.
-- 1. b. Incorrect.
(++) [1,2,3] [4,5,6]
-- 1. c. Correct.
-- 1. d. Incorrect.
["hello" ++ " world"]
-- 1. e. Incorrect.
"hello" !! 4
-- 1. f. Correct.
-- 1. g. Incorrect
take 4 "lovely"
-- 1. h. Correct.

-- 2. a => d.
[6,12,18]
-- 2. b => c.
"rainbow"
-- 2. c => e.
10
-- 2. d => a.
"Jules"
-- 2. e => b.
[2,3,5,6,8,9]
```

## Building functions

```haskell
-- 1. a.
"Curry is awesome" ++ "!"
-- 1. b.
take 1 (drop 4 "Curry is awesome!")
-- 1. c.
drop 9 "Curry is awesome!"

-- 2. a.
bang :: String -> String
bang s = s ++ "!"
-- 2. b.
fifth :: String -> String
fifth s = take 1 (drop 4 s)
-- 2. c.
last :: String -> String
last = drop 9

-- 3.
thirdLetter :: String -> Char
thirdLetter x = x !! 2

-- 4.
letterIndex :: Int -> Char
letterIndex x = "Curry is awesome!" !! x

-- 5.
rvrs :: String -> String
rvrs x = a ++ b ++ c
  where
    a = drop 9 x
    b = take 4 (drop 5 x)
    c = take 5 x
```
