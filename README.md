# doc
###【Figma 教學】[Figma 設計新手指南！](https://projectmanager.com.tw/%e5%b7%a5%e5%85%b7/figma-%e6%95%99%e5%ad%b8/)最全功能詳解+費用總結！
### 【Markdown】 [中文說明文件](https://markdown.tw/)
### 技術筆記好工具：[Markdown語法&編輯器](https://hackmd.io/@howkii-studio/markdown_intro)
# 第一層級標題
## 第二層級標題
### 第三層級標題
#### 第四層級標題
##### 第五層級標題
###### 第六層級標題

**加粗** </p> 
*斜體*

> 引用內容

```C= 
printf("Hello")
```

print("Hello")

```python=
print("Hello');
```


| 第 1 行   | 第 2行 2 | 第 3 行  |
| -------- | -------- | -------- |
| info     | Text     | Text     |
| info     | Text     | Text     |
| info     | Text     | Text     |
| info     | Text     | Text     |

**7. 資訊區塊**
| 區塊類型 | 背景顏色 |
| ------  | ------ |
| info    | 淺藍色 |
| success | 淺綠色 |
| danger  | 淺紅色 |
| warning | 淺黃色 |

```
::: info
    重要資訊
:::
```
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.


好的，當然可以。

由於 C 語言是 C++ 的基礎，它們在處理變數、運算和流程控制方面非常相似，但 C 語言在**輸入/輸出 (I/O)** 和**數據結構**方面有不同的語法（主要使用 `stdio.h` 而非 `iostream`）。

我將為您提供一份完整的 **C 語言講義**，內容涵蓋您前述 7 個問題的核心概念，並提供一個可以完整運行的程式碼。

-----

# 📚 C 語言編程入門講義：基礎概念與實踐

本講義根據您的七個 BASIC 練習題，對應講解 C 語言中變數、運算、輸入/輸出和循環的基礎知識。

## 🎯 預備知識：C 語言基本結構

在 C 語言中，我們使用 `printf()` 進行輸出，使用 `scanf()` 進行輸入，這兩個函數都來自標準輸入/輸出庫 `<stdio.h>`。

```c
#include <stdio.h> // 引入標準輸入/輸出函式庫

// 程式執行入口點
int main() {
    // 程式碼寫在這裡
    
    return 0; // 程式成功結束
}
```

-----

## 💻 階段一：變數與基本運算 (問題 1, 2)

### 📌 C 語言數據類型

  * **`int`**: 儲存整數 (e.g., 3, -10)。
  * **`float` / `double`**: 儲存浮點數/小數 (e.g., 2.66, 144.0)。

### 📌 問題 1：數值常數計算

**要求：** 計算 $8 \times 3$, $8 \div 3$, $8 + 3$，將結果存入 A1, A2, A3 並輸出。

```c
// 解決 問題 1
double A1, A2, A3;

A1 = 8 * 3;
// 確保使用浮點數除法 8.0 / 3.0
A2 = 8.0 / 3.0; 
A3 = 8 + 3;

// 輸出使用 printf。%f 格式化浮點數，\n 換行。
printf("--- 問題 1 結果 ---\n");
printf("A1 (8 * 3) = %.2f\n", A1);
printf("A2 (8 / 3) = %.2f\n", A2);
printf("A3 (8 + 3) = %.2f\n", A3);
```

### 📌 問題 2：使用變數進行運算

**要求：** 設 $A=8, B=2$，計算 $A \times B, A \div B, A - B$，存入 A1, A2, A3 並輸出。

```c
// 解決 問題 2
int A = 8;
int B = 2;
double B1, B2, B3;

B1 = A * B;
// 使用 (double) 進行強制類型轉換，確保 B2 為浮點數結果
B2 = (double)A / B; 
B3 = A - B;

printf("\n--- 問題 2 結果 ---\n");
printf("變數 A=%d, B=%d\n", A, B); // %d 格式化整數
printf("B1 (A * B) = %.2f\n", B1);
printf("B2 (A / B) = %.2f\n", B2);
printf("B3 (A - B) = %.2f\n", B3);
```

-----

## 🕹 階段二：用戶互動輸入 (問題 3, 7)

### 📌 問題 3：從用戶獲取輸入（INPUT）

**要求：** 讀入 A, B 值，計算 $A \times B, A - B, A \div B$，並輸出。

在 C 語言中，我們使用 **`scanf()`** 來接收用戶輸入，並需要使用 **`&` 符號**來指定變數的內存地址。

```c
// 解決 問題 3
double InputA, InputB; 
double C1, C2, C3;

printf("\n--- 問題 3: 請輸入 A, B 數值 ---\n");

// 提示用戶輸入
printf("請輸入 A 的數值: ");
// %lf 讀取 double 類型 (注意 C 語言 float/double 的格式化符號差異)
scanf("%lf", &InputA); 

printf("請輸入 B 的數值: ");
scanf("%lf", &InputB); 

// 執行計算
C1 = InputA * InputB;
C2 = InputA - InputB;

printf("\nA * B = %.2f\n", C1);
printf("A - B = %.2f\n", C2);

if (InputB != 0) {
    C3 = InputA / InputB;
    printf("A / B = %.2f\n", C3);
} else {
    printf("A / B: 錯誤 (除數為零)\n");
}
```

### 📌 問題 7：輸出格式控制 (PRINT)

**要求：** 讀進 $X$，輸出 $X^2$，並思考如何適當安排 `PRINT`。

```c
// 解決 問題 7
double X, Y;
    
printf("\n--- 問題 7: 計算平方與格式化輸出 ---\n");
printf("請輸入一個數值 X: ");
scanf("%lf", &X);

Y = X * X;

printf("\n輸出結果:\n");
printf("X 值\tX^2 值\n"); // \t 符號代表 Tab 鍵，用於對齊
printf("%.2f\t%.2f\n", X, Y);
```

-----

## 🔄 階段三：程式流程控制 (問題 4, 5, 6)

### 📌 問題 4：重複執行（for 循環）

**要求：** 連續讀進 3 個數目，計算其平方。

在 C 語言中，**`for` 循環** 用於重複執行一段代碼指定的次數。

```c
// 解決 問題 4
printf("\n--- 問題 4: 連續計算 3 個數目的平方 (for 迴圈) ---\n");

// for 循環，執行 i=1, 2, 3 共三次
for (int i = 1; i <= 3; ++i) {
    double Num;
    double Square;

    printf("第 %d 次 - 請輸入數值: ", i);
    scanf("%lf", &Num);

    Square = Num * Num;

    printf("數值 %.2f 的平方是: %.2f\n", Num, Square);
}
```

### 📌 問題 5 & 6：批次數據處理（數組 / 模擬 READ/DATA）

**要求：** 使用 `READ/DATA` 讀取多組 A, B 值並計算 $A \times B$。

在 C 語言中，我們使用 **數組 (Arrays)** 來預存多組數據，以模擬 BASIC 的 `DATA` 語句。

```c
// 解決 問題 5 (模擬 READ/DATA)
// 使用 C 語言數組 (Array) 儲存資料
// 模擬 DATA 3, 4, 5 和 DATA 4, 9, 9
int DataA[] = {3, 4, 5};
int DataB[] = {4, 9, 9};
int array_size = sizeof(DataA) / sizeof(DataA[0]); // 計算數組長度

printf("\n--- 問題 5 & 6: 模擬 READ/DATA 批次處理 ---\n");

printf("  A\t  B\t A * B\n");
printf("-----------------------\n");

// 循環 array_size 次 (即 3 次)
for (int i = 0; i < array_size; ++i) {
    int CurrentA = DataA[i]; // 讀取 DataA 中的第 i 個元素
    int CurrentB = DataB[i]; // 讀取 DataB 中的第 i 個元素
    int Result = CurrentA * CurrentB;

    // \t 模擬表格對齊，%d 輸出整數
    printf(" %d\t %d\t %d\n", CurrentA, CurrentB, Result);
}
printf("-----------------------\n");
printf(" (問題 6 說明: C 語言數組也是依序讀取數據，與 BASIC DATA 概念一致。)\n");
```

-----

## 完整的 C 語言程式碼

您可以將這段程式碼複製並存為 `.c` 文件（例如 `c_tutorial.c`），然後使用 C 編譯器（如 GCC）進行編譯和執行。

```c
#include <stdio.h>
#include <stdlib.h> // 為了使用 exit() 處理錯誤 (非必須，但建議)

// 程式執行入口點
int main() {
    // 設置輸出格式，讓浮點數顯示小數點後兩位
    // C 語言的 printf("%f") 預設精度高，使用 %.2f 鎖定兩位
    
    // =================================================================
    // 問題 1: 數值常數計算
    // =================================================================
    printf("=================================================\n");
    printf("【問題 1】: 數值常數計算\n");
    double A1, A2, A3;

    A1 = 8 * 3;
    A2 = 8.0 / 3.0; 
    A3 = 8 + 3;

    printf("A1 (8 * 3) = %.2f\n", A1);
    printf("A2 (8 / 3) = %.2f\n", A2);
    printf("A3 (8 + 3) = %.2f\n", A3);


    // =================================================================
    // 問題 2: 使用變數進行運算
    // =================================================================
    printf("\n=================================================\n");
    printf("【問題 2】: 使用變數進行運算 (A=8, B=2)\n");
    int A = 8;
    int B = 2;
    double B1, B2, B3;

    B1 = A * B;
    B2 = (double)A / B; 
    B3 = A - B;

    printf("變數 A=%d, B=%d\n", A, B); 
    printf("B1 (A * B) = %.2f\n", B1);
    printf("B2 (A / B) = %.2f\n", B2);
    printf("B3 (A - B) = %.2f\n", B3);


    // =================================================================
    // 問題 3: 從用戶獲取輸入 (INPUT)
    // =================================================================
    printf("\n=================================================\n");
    printf("【問題 3】: 從用戶獲取輸入 (A, B)\n");
    double InputA, InputB; 
    double C1, C2, C3;

    printf("請輸入 A 的數值: ");
    if (scanf("%lf", &InputA) != 1) { // 檢查輸入是否成功
        printf("輸入錯誤，程式終止。\n");
        return 1;
    }

    printf("請輸入 B 的數值: ");
    if (scanf("%lf", &InputB) != 1) {
        printf("輸入錯誤，程式終止。\n");
        return 1;
    }
    
    C1 = InputA * InputB;
    C2 = InputA - InputB;

    printf("\nA * B = %.2f\n", C1);
    printf("A - B = %.2f\n", C2);

    if (InputB != 0) {
        C3 = InputA / InputB;
        printf("A / B = %.2f\n", C3);
    } else {
        printf("A / B: 錯誤 (除數為零)\n");
    }


    // =================================================================
    // 問題 7: 輸出格式控制 (PRINT X 和 X^2)
    // =================================================================
    printf("\n=================================================\n");
    printf("【問題 7】: 計算平方與格式化輸出\n");
    double X, Y;
    
    printf("請輸入一個數值 X: ");
    if (scanf("%lf", &X) != 1) {
        printf("輸入錯誤，程式終止。\n");
        return 1;
    }

    Y = X * X;

    printf("\n輸出結果:\n");
    printf("X 值\tX^2 值\n");
    printf("%.2f\t%.2f\n", X, Y);


    // =================================================================
    // 問題 4: 重複執行（for 循環）
    // =================================================================
    printf("\n=================================================\n");
    printf("【問題 4】: 連續計算 3 個數目的平方 (for 迴圈)\n");

    for (int i = 1; i <= 3; ++i) {
        double Num;
        double Square;

        printf("第 %d 次 - 請輸入數值: ", i);
        if (scanf("%lf", &Num) != 1) {
             // 假設用戶在循環中輸入錯誤，僅跳過當前循環或退出
             printf("輸入錯誤，程式終止。\n");
             return 1; 
        }

        Square = Num * Num;

        printf("數值 %.2f 的平方是: %.2f\n", Num, Square);
    }


    // =================================================================
    // 問題 5 & 6: 批次數據處理（模擬 READ/DATA）
    // =================================================================
    printf("\n=================================================\n");
    printf("【問題 5 & 6】: 模擬 READ/DATA 批次處理\n");

    int DataA[] = {3, 4, 5};
    int DataB[] = {4, 9, 9};
    // 獲取數組大小 (元素個數)
    int array_size = sizeof(DataA) / sizeof(DataA[0]); 

    printf("  A\t  B\t A * B\n");
    printf("-----------------------\n");

    for (int i = 0; i < array_size; ++i) {
        int CurrentA = DataA[i]; 
        int CurrentB = DataB[i];
        int Result = CurrentA * CurrentB;

        printf(" %d\t %d\t %d\n", CurrentA, CurrentB, Result);
    }
    printf("-----------------------\n");
    
    printf("\n程式執行完畢，謝謝使用！\n");
    printf("=================================================\n");

    return 0;
}
```

好的，這是一個很好的要求。我將根據您提供的 7 個問題的解析結果，將 **變數、運算、輸入/輸出** 和 **流程控制** 的概念，彙整成一份適用於初學者的 **C++ 講義**。

由於原始教材基於 BASIC 語言，我會將其概念對應到現代 C++ 語法，並側重於核心邏輯。

-----

# 📚 C++ 編程入門講義：基礎概念與實踐

本講義根據您的七個 BASIC 練習題，對應講解 C++ 中變數、運算、輸入/輸出和循環的基礎知識。

## 🎯 預備知識：C++ 基本結構

在 C++ 中，所有的程式碼都寫在 `main` 函數中，並需要引入輸入輸出庫 `<iostream>`。

```cpp
#include <iostream> // 引入標準輸入/輸出函式庫
#include <cmath>    // 引入數學函式庫 (用於一些複雜運算，雖然本講義用不到)

// 使用 std 命名空間，可以簡化程式碼
using namespace std;

// 程式執行入口點
int main() {
    // 程式碼寫在這裡

    return 0; // 程式成功結束
}
```

-----

## 💻 階段一：變數與基本運算 (問題 1, 2)

### 📌 問題 1：數值常數計算

**要求：** 計算 $8 \times 3$, $8 \div 3$, $8 + 3$，將結果存入 A1, A2, A3 並輸出。

在 C++ 中，我們必須先**聲明 (Declare)** 變數的**數據類型**（例如 `int` 處理整數，`double` 處理浮點數）。

```cpp
// 解決 問題 1
// 由於除法 8 / 3 會產生小數，我們使用 double 類型來儲存結果。
double A1, A2, A3;

// 執行計算並賦值
A1 = 8 * 3;
A2 = 8.0 / 3.0; // 確保除數和被除數是浮點數，才能得到浮點數結果
A3 = 8 + 3;

// 輸出結果 (C++ 使用 cout)
cout << "--- 問題 1 結果 ---" << endl;
cout << "A1 (8 * 3) = " << A1 << endl;
cout << "A2 (8 / 3) = " << A2 << endl;
cout << "A3 (8 + 3) = " << A3 << endl;
```

### 📌 問題 2：使用變數進行運算

**要求：** 設 $A=8, B=2$，計算 $A \times B$, $A \div B$, $A - B$，存入 A1, A2, A3 並輸出。

```cpp
// 解決 問題 2
// 聲明並初始化變數 A 和 B
int A = 8;
int B = 2;

// 由於結果 A/B 是整數，A*B 是整數，使用 int 即可（但 A/B 仍需注意浮點數問題）
// 這裡我們直接使用 double 確保除法結果精確
double B1, B2, B3;

B1 = A * B;
B2 = (double)A / B; // 使用 (double) 進行強制類型轉換，確保執行浮點數除法
B3 = A - B;

cout << "\n--- 問題 2 結果 ---" << endl;
cout << "A = " << A << ", B = " << B << endl;
cout << "B1 (A * B) = " << B1 << endl;
cout << "B2 (A / B) = " << B2 << endl;
cout << "B3 (A - B) = " << B3 << endl;
```

-----

## 🕹 階段二：用戶互動輸入 (問題 3, 7)

### 📌 問題 3：從用戶獲取輸入（INPUT）

**要求：** 讀入 A, B 值，計算 $A \times B, A - B, A \div B$，存入 A1, A2, A3 並輸出。

在 C++ 中，我們使用 `cin` (Character In) 來接收用戶在終端機的輸入。

```cpp
// 解決 問題 3
double C1, C2, C3;
double InputA, InputB; // 用於儲存用戶輸入的 A 和 B

cout << "\n--- 問題 3: 請輸入 A, B 數值 ---" << endl;

// 提示用戶輸入 A
cout << "請輸入 A 的數值: ";
cin >> InputA; // 從控制台讀取數值到 InputA

// 提示用戶輸入 B
cout << "請輸入 B 的數值: ";
cin >> InputB; // 從控制台讀取數值到 InputB

// 執行計算
C1 = InputA * InputB;
C2 = InputA - InputB;
C3 = InputA / InputB;

cout << "\n--- 問題 3 結果 ---" << endl;
cout << "A * B = " << C1 << endl;
cout << "A - B = " << C2 << endl;
cout << "A / B = " << C3 << endl;
```

### 📌 問題 7：輸出格式控制 (PRINT)

**要求：** 讀進 $X$，輸出 $X^2$，並思考如何適當安排 `PRINT`。

在 C++ 中，我們使用 `cout` 和一些格式控制符（如 `<<`）來控制輸出格式。

```cpp
// 解決 問題 7
double X;

cout << "\n--- 問題 7: 計算平方與格式化輸出 ---" << endl;
cout << "請輸入一個數值 X: ";
cin >> X;

double Y = X * X;

// 在 C++ 中，endl 或 \n 用於換行。
// 變數之間的分隔，由你自己在字串中加入空格或 Tab (\t) 來控制。
cout << "\n輸出格式範例 (使用 Tab 分隔):" << endl;
cout << "X 值\tX^2 值" << endl;
cout << X << "\t" << Y << endl;
```

-----

## 🔄 階段三：程式流程控制 (問題 4, 5, 6)

### 📌 問題 4：重複執行（GOTO / 循環）

**要求：** 連續讀進 3 個數目，計算其平方。

在現代 C++ 中，我們使用 **`for` 循環**來取代 BASIC 中的 `GOTO`，這使程式碼更清晰、更安全。

```cpp
// 解決 問題 4
cout << "\n--- 問題 4: 連續計算 3 個數目的平方 (使用 for 迴圈) ---" << endl;

// 使用 for 循環重複執行 3 次
for (int i = 1; i <= 3; ++i) {
    double Num;
    double Square;

    cout << "\n第 " << i << " 次 - 請輸入數值: ";
    cin >> Num;

    Square = Num * Num;

    cout << "數值 " << Num << " 的平方是: " << Square << endl;
}
```

### 📌 問題 5 & 6：批次數據處理（READ/DATA / 數組）

**要求：** **問題 5** 要求使用 `READ/DATA` 讀取多組 A, B 值並計算 $A \times B$。**問題 6** 證明 DATA 語句在 BASIC 中是連續的。

在 C++ 中，我們使用 **數組 (Arrays)** 或 **向量 (Vectors)** 來預存多組數據，然後使用循環來「讀取」它們。這模擬了 `DATA` 語句的功能。

```cpp
// 解決 問題 5 (模擬 READ/DATA)
// 使用 C++ 向量 (vector) 儲存資料
#include <vector> // 需要引入此標頭檔

// 模擬 DATA 3, 4, 5 和 DATA 4, 9, 9
vector<int> DataA = {3, 4, 5};
vector<int> DataB = {4, 9, 9};

cout << "\n--- 問題 5: 模擬 READ/DATA 批次處理 ---" << endl;
cout << "  A |  B | A * B" << endl;
cout << "----|----|------" << endl;

// 使用 for 循環和索引來讀取每一組 A 和 B
for (size_t i = 0; i < DataA.size(); ++i) {
    int A = DataA[i]; // 讀取 DataA 中的第 i 個元素
    int B = DataB[i]; // 讀取 DataB 中的第 i 個元素
    int Result = A * B;

    // 使用 C++ 的格式化輸出，\t 代表 Tab (模擬欄位分隔)
    cout << " " << A << "\t " << B << "\t " << Result << endl;
}

// 解決 問題 6 (BASIC DATA 概念)
// 由於 C++ 沒有 READ/DATA，但其核心概念是「數據流的連續性」。
// 程式 1 和 程式 2 結果相同，在 C++ 中意味著只要數據在容器中是連續的，
// 無論你如何聲明，循環都會依序訪問它們，驗證了數據流的連續性。
```

-----

## 整合程式碼

如果您想將所有程式碼放在一個文件中運行，您可以將上述所有程式碼段按順序放入一個 `main` 函數中。

### **總結與下一步**

這份講義涵蓋了：

1.  **變數聲明 (`int`, `double`)**
2.  **基本運算 (`*`, `/`, `+`, `-`)**
3.  **輸入/輸出 (`cin`, `cout`)**
4.  **循環 (`for` 迴圈)**
5.  **數據結構 (`vector` 模擬 DATA)**

**您是否希望我提供一個完整的 C++ 程式碼檔案，包含上述所有問題的解決方案，以便您直接編譯和運行？**
