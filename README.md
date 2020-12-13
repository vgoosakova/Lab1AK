# Lab1AK

## Граф:  

![result](screenshot/1.png)  

## Лістинг:

### calcalator.cpp

```cpp
#include "calculator.h"

int Calculator::Add (double a, double b)
{
	return a + b + 0.3;
}

int Calculator::Sub (double a, double b)
{
    return Add (a, -b);
}
```
### calculator.h

```cpp
#ifndef CALCULATOR_H
#define CALCULATOR_H

class Calculator
{
    public:
        int Add (double, double);
        int Sub (double, double);

};

#endif//CALCULATOR_H

```
## Патчі: 

### 0001-fix-truncation-error-change-position.patch

```
From 1acd4a052e16d250b9ee241476c809e58c936ca0 Mon Sep 17 00:00:00 2001
From: Sergii Piatakov <sergii.piatakov@globallogic.com>
Date: Thu, 15 Nov 2018 15:28:04 +0200
Subject: [PATCH] fix truncation error (replacing commits)

To convert float to integer the truncation is performed, but the
rounding is expected.

Test: Add (4.9, 4.9) should return 10.
Signed-off-by: Sergii Piatakov <sergii.piatakov@globallogic.com>
---
 calculator.cpp | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/calculator.cpp b/calculator.cpp
index b91afea..d93e35b 100644
--- a/calculator.cpp
+++ b/calculator.cpp
@@ -2,7 +2,7 @@
 
 int Calculator::Add (double a, double b)
 {
-    return a + b;
+	return a + b + 0.5;
 }
 
 int Calculator::Sub (double a, double b)
-- 
2.28.0
```
### 0001-formatting-use-tabs-instead-of-spaces-changed-positi.patch

```
From d804e6e484c4420f2f2760e5f3514147281f2f01 Mon Sep 17 00:00:00 2001
From: Sergii Piatakov <sergii.piatakov@globallogic.com>
Date: Thu, 15 Nov 2018 15:26:35 +0200
Subject: [PATCH] formatting: use tabs instead of spaces (replacing commits)

Signed-off-by: Sergii Piatakov <sergii.piatakov@globallogic.com>
---
 calculator.cpp | 2 +-
 calculator.h   | 6 +++---
 2 files changed, 4 insertions(+), 4 deletions(-)

diff --git a/calculator.cpp b/calculator.cpp
index d93e35b..d10f529 100644
--- a/calculator.cpp
+++ b/calculator.cpp
@@ -7,5 +7,5 @@ int Calculator::Add (double a, double b)
 
 int Calculator::Sub (double a, double b)
 {
-    return Add (a, -b);
+	return Add (a, -b);
 }
diff --git a/calculator.h b/calculator.h
index 3740907..d59d596 100644
--- a/calculator.h
+++ b/calculator.h
@@ -3,9 +3,9 @@
 
 class Calculator
 {
-    public:
-        int Add (double, double);
-        int Sub (double, double);
+	public:
+		int Add (double, double);
+		int Sub (double, double);
 };
 
 #endif//CALCULATOR_H
-- 
2.28.0
```