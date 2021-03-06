# Sean Python 學習課程教材
Learning Python tutorials and materials<br>
<h2>Control Flow Statements: if</h2>
什麼是程式？<br><br>
<strong>"Algorithms + Data Structures = Programs"</strong> by Niklaus Wirth (1976) - 1984 Turing Award<br>
處理（控制）流程 + 資料：就是程式！<br><br>
if 敘述是最常用的控制流程判斷式，以下是 if 敘述的內容和結構。<br><br>
<h3>if 敘述：</h3>

```Python
if condition expression:
	statement(s)
elif condition expression:
	statement(s)
else:
	statement(s)
```
<h3>結構說明：</h3>
**if** - if 敘述關鍵字，必要。<br><br>
**condition express** - 條件判斷式，必要。<br><br>
<strong>:</strong> - Python 敘述結尾符號，必要。<br><br>
<strong>statement(s)</strong> - 若符合條件時要執行的動作敘述，必須內縮(縮排)，必要。<br><br>
<strong>elif</strong> - 若 if 的條件不符合，就再判斷這個條件，非必要。<br><br>
<strong>else</strong> - 若前述的條件統統都不符合，就執行這裡的動作，非必要。<br><br>
<h3>範例：</h3>

```Python
if 5 > 2:   # 如果 (5 > 2)，則印出 "5 > 2 為真(True)"
	print("5 > 2 為真(True)")
```

5 > 2 就是 condition express(條件判斷式)，這個判斷式的結果若為真(True) / 成立，就是條件符合，則會執行 print("5 > 2 為真(True)") 這個動作敘述 statement(s)；若結果是偽(False) / 假 / 不成立，就是條件不符合，則不執行其動作敘述。<br>
和Java不同，Python的 condition express(條件判斷式)外小括號是非必要的，加了也沒關係。<br>
condition express(條件判斷式)的內容是由： <strong>運算元</strong> 及 <strong>關係運算子 / 邏輯運算子</strong> 所組成。前述例子的 5 > 2，5 和 2 就是運算元，是被運算判斷的元素； > (大於)是關係運算子。<br>
接下來要介紹關係運算子和邏輯運算子。<br>
<h3>關係運算子(Relational Operators)：</h3>
<h3>邏輯運算子(Logical Operators)：</h3>
