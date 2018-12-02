# Chapter 6

## Eq Instances

```haskell
-- 1.
data TisAnInteger = TisAn Integer
instance Eq TisAnInteger where
  (==) (TisAn x) (TisAn y) = x == y
-- 2.
data TwoIntegers = Two Integer Integer
instance Eq TwoIntegers where
  (==) (Two x y) (Two x' y') = x == x' && y == y'
-- 3.
data StringOrInt = TisAnInt Int | TisAString String
instance Eq StringOrInt where
  (==) (TisAnInt x) (TisAnInt y) = x == y
  (==) (TisAString x) (TisAString y) = x == y
-- 4.
data Pair a = Pair a a
instance Eq a => Eq (Pair a) where
  (==) (Pair v v') (Pair u u') = v == u && v' == u'
-- 5.
data Tuple a b = Tuple a b
instance (Eq a, Eq b) => Eq (Tuple a b) where
  (==) (Tuple x y) (Tuple x' y') = x == x' && y == y'
-- 6.
data Which a = ThisOne a | ThatOne a
instance Eq a => Eq (Which a) where
  (==) (ThisOne x) (ThisOne y) = x == y
  (==) (ThatOne x) (ThatOne y) = x == y
  (==) _ _ = False
-- 7.
data EitherOr a b = Hello a | Goodbye b
instance (Eq a, Eq b) => Eq (EitherOr a b) where
  (==) (Hello x) (Hello y) = x == y
  (==) (Goodbye x) (Goodbye y) = x == y
  (==) _ _ = False
```

## Will They Work?

```haskell
-- 1.
Prelude> max (length [1, 2, 3]) (length [8, 9, 10, 11, 12])
5
-- 2.
Prelude> compare (3 * 4) (3 * 5)
LT
-- 3. Incorrect.
-- 4.
Prelude> (5 + 3) > (3 + 6)
False
```
