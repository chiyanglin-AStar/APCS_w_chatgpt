我們從 **輸入與輸出 (Input and Output)** 開始。這是 C 語言的基礎，掌握好輸入與輸出對後續學習很重要。  

## **輸入與輸出 (Input and Output)**
C 語言主要使用 `printf()` 來輸出，`scanf()` 來輸入。此外，`gets()` 和 `puts()` 也可以用來處理字串輸入輸出。

### **範例 1：輸出文字**
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
**解釋**：
- `printf()` 用於輸出文字，`\n` 代表換行。

---

### **範例 2：輸入與輸出整數**
```c
#include <stdio.h>

int main() {
    int num;
    printf("請輸入一個整數: ");
    scanf("%d", &num);
    printf("你輸入的數字是: %d\n", num);
    return 0;
}
```
**解釋**：
- `scanf("%d", &num);` 讀取使用者輸入的整數。
- `&num` 代表變數的記憶體位置，確保 `scanf()` 正確存入數值。

---

### **範例 3：輸入與輸出浮點數**
```c
#include <stdio.h>

int main() {
    float num;
    printf("請輸入一個浮點數: ");
    scanf("%f", &num);
    printf("你輸入的數字是: %.2f\n", num);
    return 0;
}
```
**解釋**：
- `%f` 用於輸入浮點數，`%.2f` 表示輸出時顯示 2 位小數。

---

### **範例 4：輸入與輸出字元**
```c
#include <stdio.h>

int main() {
    char ch;
    printf("請輸入一個字元: ");
    scanf(" %c", &ch);  // 注意前面的空格
    printf("你輸入的字元是: %c\n", ch);
    return 0;
}
```
**解釋**：
- `%c` 用於讀取單一字元。
- `scanf(" %c", &ch);` 前面加空格是為了忽略前一次輸入的換行符號。

---

### **範例 5：輸入與輸出字串**
```c
#include <stdio.h>

int main() {
    char str[100];
    printf("請輸入一個字串: ");
    scanf("%s", str);
    printf("你輸入的字串是: %s\n", str);
    return 0;
}
```
**解釋**：
- `%s` 用於讀取字串，但 `scanf("%s", str);` 只能讀取單一單詞，遇到空格會停止。

---

### **範例 6：使用 `gets()` 和 `puts()` 處理字串**
```c
#include <stdio.h>

int main() {
    char str[100];
    printf("請輸入一個句子: ");
    gets(str);
    printf("你輸入的句子是: ");
    puts(str);
    return 0;
}
```
**解釋**：
- `gets(str);` 允許讀取整行字串（包含空格）。
- `puts(str);` 直接輸出字串並換行。

⚠ **注意**：`gets()` 可能會造成緩衝區溢位 (Buffer Overflow)，建議改用 `fgets()`。

---

### **範例 7：使用 `fgets()` 來安全讀取字串**
```c
#include <stdio.h>

int main() {
    char str[100];
    printf("請輸入一個句子: ");
    fgets(str, sizeof(str), stdin);
    printf("你輸入的句子是: %s", str);
    return 0;
}
```
**解釋**：
- `fgets(str, sizeof(str), stdin);` 讀取包含空格的字串，確保不超過陣列大小，避免溢位問題。

---

你可以先試試這些範例，看看有沒有問題或需要補充的部分！如果沒問題，我們可以進入下一個單元 **算術運算 (Arithmetic Operation)** 🚀
