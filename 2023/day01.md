**[Day 1: Trebuchet?!](https://adventofcode.com/2023/day/1)**

_(Input expected in A:A)_

**Part 1 & 2**

```py
={SUMPRODUCT(LET(r,REGEXREPLACE(TOCOL(A:A,1),"\D",),LEFT(r)&RIGHT(r))),
  SUMPRODUCT(
    LET(n,{"one";"two";"three";
          "four";"five";"six";
          "seven";"eight";"nine"},
        r,REGEXREPLACE(
            REDUCE(
              A:A,
              ROW(1:9),
              LAMBDA(a,i,SUBSTITUTE(a,INDEX(n,i),INDEX(n&ROW(1:9)&n,i)))),
            "\D",),
        LEFT(r)&RIGHT(r)))
 }
```
