# Chapter 1 Solutions

## Intermission: Equivalence Exercises

```
1. b. λxy.xz ≡ λmn.mz
2. c. λxy.xxy ≡ λa.(λb.aab)
3. b. λxyz.zx ≡ λtos.st
```

## Combinators

```
1. λx.xxx is a combinator.
2. λxy.zx is not a combinator because z is a free variable.
3. λxyz.xy(zx) is a combinator.
4. λxyz.xy(zxy) is a combinator
5. λxy.xy(zxy) is not a combinator because z is a free variable.
```

## Normal form or diverge?

```
1. λx.xxx is normal form.
2. (λz.zz)(λy.yy) ≡
   (λy.yy)(λy.yy) ≡
   (λy.yy)(λy.yy) is divergent.
3. (λx.xxx)z ≡ zzz is normal form.
```

## Beta reduce

```
1. (λabc.cba)zz(λwv.w) ≡
   (λbc.cbz)z(λwv.w) ≡
   (λc.czz)(λwv.w) ≡
   (λwv.w)zz ≡
   (λv.z)z ≡
   z

2. (λx.λy.xyy)(λa.a)b ≡
   (λy.(λa.a)yy)b ≡
   (λa.a)bb ≡
   bb

3. (λy.y)(λx.xx)(λz.zq) ≡
   (λx.xx)(λz.zq) ≡
   (λz.zq)(λz.zq) ≡
   (λz.zq)q ≡
   qq

4. (λz.z)(λz.zz)(λz.zy) ≡
   (λz.zz)(λz.zy) ≡
   (λz.zy)(λz.zy) ≡
   (λz.zy)y ≡
   yy

5. (λx.λy.xyy)(λy.y)y ≡
   (λy.(λy.y)yy)y ≡
   (λy.yy)y ≡
   yy

6. (λa.aa)(λb.ba)c ≡
   (λb.ba)(λb.ba)c ≡
   (λb.ba)ac ≡
   aac

7. (λxyz.xz(yz))(λx.z)(λx.a) ≡
   (λyz.(λx.z')z(yz))(λx.a) ≡
   (λz.(λx.z')z((λx.a)z)) ≡
   (λz.z'((λx.a)z)) ≡
   (λz.z'a)
```
