# 脚本语句 
这些语句在对象编程编辑器的左栏中。这些语句执行 Neuron 程序的表达。语句右边一列的所有内容（如果没有新的语句，则在下一行）都属于这个语句。

## 注释 
这句话对系统没有任何意义。这只是对操作者的注释。它也可以用来暂时删除其他语句，以避免某些操作。

例如：

| 注释 | \*\*\* 这是一个描述的注释    |
| ---- | ---------------------------- |
|      | \*\*\* 如何使用 COMMENT 语句 |

## 声明 
对于所有的局部变量，在子程序中使用之前，应该先声明它。所有局部变量只在局部脚本中使用。

## POS 
此语句在此位置标记了一个标签号（1-999），可用于 GOTO 指令（见下文）。当到达此语句时，没有任何操作。右栏中的文字被当作注释。

例如：

|        |                                 |
| ------ | ------------------------------- |
| POS120 | \* 如果例行程序结束，则回到这里 |

## DO 
该语句无条件地执行其表达式。表达式用 ";" 分隔。

例如：

| 注释 | \*\*\* 调用带参数的子程序 |
| ---- | ------------------------- |
| DO   | valuein = 12; CALL SR210; |

## IF-THEN-ELSEIF-THEN-ELSE 
该语句有条件地执行其表达式。表达式之间用 ";" 隔开。

完整的语法是 IF 表达式 THEN 行为表达式；行为表达式；ELSE IF 表达式 THEN 行为表达式；行为表达式；ELSE 行为表达式；行为表达式。

如果 IF 表达式为真（非零），系统执行 THEN 之后的表达式，然后跳过其余的 IF-THEN-ELSE 语句。

如果 IF 表达式为假（零），系统跳过 THEN 语句，寻找 ELSE 或 ELSE IF 语句（如果有）。如果下一条语句是 ELSE IF，系统将其作为 IF 语句处理（IF-THEN-ELSE 的开始）。如果下一条语句是 ELSE，系统就会执行表达式。

例如：

| 注释    | \*\*\* 检查第 10 和 25 号 St |
| ------- | ---------------------------- |
| IF      | st == 10                     |
| THEN    | st = 11;                     |
| ELSE IF | st == 25                     |
| THEN    | st = 26;                     |
