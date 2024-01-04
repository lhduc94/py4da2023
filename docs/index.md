--- 
title: "Python for Data Analyst 2023"
author: "Lê Huỳnh Đức"
date: "2024-01-05"
site: bookdown::bookdown_site
output: bookdown::gitbook
documentclass: book
description: "Python for Data Analyst 2023"
---

# Lời nói đầu {-}

<!--chapter:end:index.Rmd-->

# Giới thiệu Python và các công cụ hỗ trợ

<!--chapter:end:posts/01-Introduction.Rmd-->

# Lập trình với ngôn ngữ Python
## Nội dung chương
- [Khai báo biến](#khai-báo-biến)

- Các kiểu dữ liệu cơ bản: float, int, str, bool​

- Chuyển đổi dữ liệu​

- Cấu trúc dữ liệu cơ bản: List, set, tuple, dictionary​

- Toán tử số học, toán tử so sánh, toán tử logic​

- Các phương thức trên string​

- Các phương thức cho dữ liệu Datetime​

- Câu lệnh có điều kiện​

- Vòng lặp trong python​

- Function​

- Comment trong python

## Khai báo biến

### Biến là gì
Biến là vị trí bộ nhớ được dành riêng để lưu trữ dữ liệu. \
Một khi biến đã được lưu trữ, nghĩa là một khoảng không gian đã được cấp phát trong bộ nhớ đó. \
Dựa trên kiểu dữ liệu của một biến, trình thông dịch cấp phát bộ nhớ và quyết định những gì có thể được lưu trữ trong khu nhớ dành riêng đó.\
Vì thế, bằng việc gán các dữ liệu khác nhau cho các biến, bạn có thể lưu trữ số nguyên, văn bản, số thập phân cho biến\
![](images/week2/variable.png)

Để khai báo biến trong Python, ta dùng cú pháp​ `tenbien = giá trị`

```python
name = "Phạm Xuân Bách"
```

Để in giá trị của biến ra màn hình, ta dùng cú pháp `print(tenbien)`

```python
print(name)
```

```{.python_output}
Phạm Xuân Bách
```

### Tại sao phải cần khai báo biến

Hãy tưởng tượng như sau, bạn có một số dữ liệu là những con số với nhiều chữ số và các thao tác tính toán

```python
52348252408 + 523482034
```

```{.python_output}
52871734442
```

```python
52348252408 + 12312454534534
```

```{.python_output}
12364802786942
```

```python
523482034 + 12312454534534
```

```{.python_output}
12312978016568
```

Một điều mà các bạn dễ dàng nhận ra đó là những con số với nhiều chữ số gây khó khăn trong việc sử dụng vì chúng có quá nhiều chữ số, đôi lúc chúng ta cũng có thể vô tình gây sai lệnh giá trị. Vì vậy, việc tạo một biến giúp ta quản lý những giá trị này dễ dàng hơn

```python
a = 52348252408
b = 523482034
c = 12312454534534
```

Ví dụ khi tính cộng a và b

```python
a + b
```

```{.python_output}
52871734442
```

```python
a + c
```

```{.python_output}
12364802786942
```

### Các quy tắc khi đặt biến trong Python

- Tên của biến phải được bắt đầu bằng một chữ hoặc một ký tự underscore (dấu gạch dưới: _).
- Tên của biến không thể bắt đầu bằng một con số. Ngoài ký tự bắt đầu ra thì trong tên biến có thể sử dụng số, chữ và dấu gạch dưới như bình thường.
- Biến trong Python phải có tên riêng, không trùng lặp với tên của các biến đang tồn tại trên file làm việc của bạn.
- Tên biến của phân biệt chữ hoa và chữ thường như chúng mình đã đề cập trong bài viết về các lưu ý quan trọng cho người mới học Python.


Ví dụ

Đặt tên có dấu gạch dưới ở đầu 

```python
_name = "Phạm Xuân Bách"
```

Khi đặt tên biến có số ở đầu, Python sẽ báo lỗi `SyntaxError`, lỗi `SyntaxError` sẽ báo cho chúng ta biết chúng ta đang vi phạm về lỗi cú pháp

```python
1name = "Phạm Xuân Bách"
```

```{.python_output}
  Cell In[10], line 1
    1name = "Phạm Xuân Bách"
    ^
SyntaxError: invalid decimal literal
```

Chúng ta có thể đặt số trong biến ở bất kì đâu ngoại trừ ký tự bắt đầu

```python
name1 = "Phạm Xuân Bách"
```

Nếu khai báo với tên trùng biến cũ thì giá trị sẽ bị đè lên

ví dụ khi khai báo `name1 = "Phạm Xuân Bách"`, khi ta khai báo `name1 = Phạm Đình Đức`, lúc này giá trị sẽ đè lên giá trị cũ

```python
name1 = "Phạm Đình Đức"
print(name1)
```

```{.python_output}
Phạm Đình Đức
```

Ví dụ khai báo với biến viết thường `name1` và viết hoa `NAME1` thì Python sẽ hiểu là hai biến khác nhau.

```python
name1 = "Phạm Đình Đức"
NAME1 = "Phạm Xuân Bách"
print(NAME1)
print(name1)
```

```{.python_output}
Phạm Xuân Bách
Phạm Đình Đức
```

### Các cách khai báo biến trong Python

- Khai báo mỗi giá trị mỗi dòng

```python
a = 1
b = 2
c = 3
```

- Khai báo các biến cùng 1 giá trị, thay vì khai báo

```python
a = 2000
b = 2000
c = 2000
```

Ta có thể khai báo

```python
a = b = c = 2000
```

- Khai báo nhiều biến khác nhau, khác giá trị trên cùng một hàng

```python
name, age, isMale = "Phạm Xuân Bách", 23, True
```

- Khai báo giá trị biến này bằng một biến khác

```python
a = 2000
b = a
```

### In dữ liệu​

Để in dữ liệu ra màn hình, ta có thể dùng lệnh `print​()`

```python
print("Phạm Xuân Bách")
```

```{.python_output}
Phạm Xuân Bách
```

Có thể in nhiều giá trị cùng lúc bằng `print()` với các giá trị cách nhau bằng dấu `,`​

```python
a = 22
print("Phạm Xuân Bách năm nay", a, "tuổi")
```

```{.python_output}
Phạm Xuân Bách năm nay 22 tuổi
```

## Kiểu dữ liệu

Kiểu dữ liệu là một khái niệm rất quan trọng trong lập trình. Các biến có thể lưu trữ các loại dữ liệu khác nhau và mỗi  loại khác nhau có thể làm những việc khác nhau. Đối với Python, ngôn ngữ lập trình có các kiểu dữ liệu sau được tích hợp sẵn theo mặc định, cụ thể như sau:
- Text Type: str
- Numeric Types:  int, float, complex
- Boolean Type: bool
- Binary Types: bytes

Bằng việc sử dụng hàm `type()` , bạn có thể lấy bất kỳ kiểu dữ liệu nào của các đối tượng. Ví dụ:

```python
x = 5
print(type(x))
```

```{.python_output}
<class 'int'>
```

### Các kiểu dữ liệu số (numeric) trong Python

Python hỗ trợ các kiểu dữ liệu số Integer (số nguyên), Float (số thực) và Complex (số phức). Python định nghĩa các lớp là int, float và complex để lưu trữ và thao tác các kiểu dữ liệu số.

- Integer (số nguyên): viết tắt là `int`, là các số nguyên dương hoặc âm (không có phần phân số). Trong Python, số nguyên không có giới hạn độ dài. Ví dụ

```python
x = 1
y = 10
z = -10
```

- Float (số thực): biểu diễn bởi lớp `float`. Lớp này đại diện cho các số thực sử dụng dấu phẩy động (15 chữ số chính xác sau dấu thập phân). Các số thực có thể được biểu diễn bằng các ký hiệu e hoặc E, ký hiệu khoa học cho a10b

```python
x = 3.14
print(x)
y = 3E4
print(y)
print(type(y))
```

```{.python_output}
3.14
30000.0
<class 'float'>
```

- Complex (số phức): biểu diễn bởi lớp phức. Một số phức được viết dưới dạng `x + yj`. trong đó `x, y` là phần thực và `j` là phần ảo.

```python
x = 3 + 5j
y = 5j
print(x)
print(x+y)
```

```{.python_output}
(3+5j)
(3+10j)
```

Python thường làm việc với số trong cơ số 10. Để làm việc với cơ số khác ta sử dụng các tiền tố sau

- Hệ nhị phân : '0b' hoặc '0B'
- Hệ bát phân : '0o' hoặc '0O'
- Hệ thập lục phân '0x' hoặc '0X'

```python
a = 'Ob10101'
print(a)
```

```{.python_output}
Ob10101
```

### Kiểu dữ liệu chuỗi ký tự (string) trong Python

Các kiểu dữ liệu chuỗi trong Python được đặt trong dấu ngoặc kép đơn hoặc ngoặc kép. Python sẽ coi các lệnh trích dẫn đơn và kép như nhau, ví dụ như `"Hello"` tương đương với `'Hello'`

Gán chuỗi cho một biến

```python
name = "Phạm Xuân Bách"
print(name)
```

```{.python_output}
Phạm Xuân Bách
```

Chúng ta có thể khai báo chuỗi bằng nhiều dòng khác nhau, dùng ba dấu nháy kép hoặc ba dấu nháy đơn

```python
str1 = """Hôm nay trời nắng chang chang
mèo con đi học chẳng mang thứ gì
chỉ mang một chiếc bút chì.
Và mang một mẩu bánh mì con con
"""
print(str1)
```

```{.python_output}
Hôm nay trời nắng chang chang
mèo con đi học chẳng mang thứ gì
chỉ mang một chiếc bút chì.
Và mang một mẩu bánh mì con con
```

```python
str2 = '''Hôm nay trời nắng chang chang
mèo con đi học chẳng mang thứ gì
chỉ mang một chiếc bút chì.
Và mang một mẩu bánh mì con con
'''
print(str2)
```

```{.python_output}
Hôm nay trời nắng chang chang
mèo con đi học chẳng mang thứ gì
chỉ mang một chiếc bút chì.
Và mang một mẩu bánh mì con con
```

Chúng ta cũng có thể nhập chuỗi với các giá trị xuống dòng bằng kí tự `\n`

```python
str3 = "Ví Dụ xuống dòng \nXuống dòng 2"
print(str3)
```

```{.python_output}
Ví Dụ xuống dòng 
Xuống dòng 2
```

Hoặc chỉ định khoảng cách tab bằng `\t`

```python
str4 = "Ví Dụ tab \t phần 1 \t phần 2"
print(str4)
```

```{.python_output}
Ví Dụ tab 	 phần 1 	 phần 2
```

### Kiểu dữ liệu Boolean

Kiểu dữ liệu Boolean là kiểu dữ liệu chứa một trong hai giá trị
- `True` - có nghĩa là đúng
- `False` - có nghĩa là sai


Ví dụ

```python
is_male = True
print(is_male)
print(type(is_male))
```

```{.python_output}
True
<class 'bool'>
```

### Ép kiểu dữ liệu

Đôi khi chúng ta muốn chuyển đổi kiểu cho biến, chúng ta có thể áp dụng phương pháp ép kiểu trong Python. Để ép kiểu dữ liệu từ kiểu này sang kiểu khác, ta dùng hàm khởi tạo của python

- `int()`: Chuyển đổi một số `float` sang số nguyên, chuỗi kí tự chứa các kí tự số sang số nguyên

- `float()`: Chuyển số `int` sang số thập phân, chuỗi kí tự chưa các kí tự số sang số thập phân

- `str()`: Chuyển các kiểu dữ liệu như số nguyên, số thập phân sang chuỗi


Ví dụ vì vấn đề nhập liệu, mặc dù gần như toàn bộ cột dữ liệu có giá trị float như `1.2`, `1.3`, nhưng người nhập liệu nhập sai dấu `.` thành dấu `,`(ví dụ `1.2` bị nhập thành `1,2`) nên cột đó được nhận diện là `string`. Chúng ta sẽ xử lý string từ `1,2` sang `1.2` bằng phương thức `.replace()` sẽ được đề cập sau. Sau khi xử lý xong, chúng ta sẽ ép kiểu về `float`.

#### Ép kiểu  sang `int`

- Khi chuyển float sang int, kết quả trả về là phần nguyên của số đó.
Ví dụ

Ép kiểu số dương
```python
a = int(2.0)
print(a)
```

```{.python_output}
2
```

```python
a = int(2.5)
print(a)
```

```{.python_output}
2
```

Ép kiểu số âm

```python
a = int(-0.5)
print(a)
```

- Chuyển từ `str` sang `int`

```python
a = "2"
print(int(a))
```

```{.python_output}
2
```

```python
a = "-2"
print(int(a))
```

```{.python_output}
-2
```

<!--chapter:end:posts/02-Python.Rmd-->


## Bài tập


### UCLN

Viết hàm tìm Ước chung lớn nhất của hai số  nguyên dương `a`, `b`


```python
def findUCLN(a, b):
    ..
    ..
    return __
```


Test case:

|Ví dụ|Kết quả|
|:--|:----------|
|`findUCLN(50, 20)`|10|
|`findUCLN(60, 520)`|20|

**Lưu ý**: không sử dụng hàm cho sẵn `math.gcd(a, b)` 


<details><summary><b>Lời giải</b></summary>
<p>

```python
import math
def findUCLN(a, b):
    return math.gcd(a, b)
```
</p></details>

---


### BCNN

Viết hàm tìm Bội chung nhỏ nhất của hai số nguyên dương `a`, `b`

```python
def findBCNN(a, b):
    ..
    ..
    return __
```

Test case:

|Ví dụ|Kết quả|
|:--|:----------|
|`findBCNN(8, 6)`|24|
|`findBCNN(30, 520)`|1560|

**Lưu ý**: không sử dụng hàm cho sẵn `math.lcm(a, b)` 

<details><summary><b>Lời giải</b></summary>
<p>

```python
def findBCNN(a, b):
    answer = a * b // findUCLN(a, b)
    return answer
```
</p></details>

---

### GIAI_THUA

Viết hàm tìm Giai thừa của một số `n` theo công thức

$n! = 1 \times 2 \times 3 \times .. \times (n-1) \times n$

```python
def findGT(n):
    ...
    return _
```

Test case:

|Ví dụ|Kết quả|
|:--|:----------|
|`findGT(5)`|120|
|`findGT(7)`|5040|

**Lưu ý**: không sử dụng hàm cho sẵn `math.factorial(n)` 

<details><summary><b>Lời giải</b></summary>
<p>

```python
def findGT(n):
    answer = 1
    for i in range(1, n+1):
        answer *= i
    return answer
```

</p></details>
---

### CHIA_CHO_5 {.tabset}

**Mô tả**

Viết hàm tìm tất cả các số chia hết cho 5 nhưng không chia hết cho 15 nằm trong đoạn từ `[a, b]`. Kết quả trả về là một danh sách

```python
def find(a, b):
    for i in range(__, __):
        if __:
            ..
            ..
        ..
    return _
```

**Test case**

|Ví dụ|Kết quả|
|:--|:----------|
|`find(1, 40)`|[5, 10, 20, 25, 35, 40]|
|`find(10, 100)`|[10, 20, 25, 35, 40, 50, 55, 65, 70, 80, 85, 95, 100]|

<details><summary><b>Lời giải</b></summary>
<p>

```python
def find(a, b):
    answer = []
    for i in range(a, b + 1):
        if (i % 5 == 0) & (i % 3 != 0):
            answer.append(i)
    return answer
```
</p></details>

---

### PARSE_STRING_01

**Mô tả**

Viết một hàm nhận đầu vào là một danh sách các số nguyên dưới dạng chuỗi và đầu ra là một danh sách

```python
def parseString(l):
    ..
    ..
    return
```
**Test case**

|Ví dụ|Kết quả|
|:--|:----------|
|`parseString("[1, 2, 3, 4, 5]")`|[1, 2, 3, 4, 5]|
|`parseString("[-1, -2]")`|[-1, -2]|
|`parseString("[0]")`|[0]|

<details><summary><b>Lời giải</b></summary>
<p>

```python
def parseString(l):
    items = l.split(',')
    answer = []
    for i in range(len(items)):
        item = items[i].replace('[','').replace(']','').strip() 
        item = int(item)
        answer.append(item)
    return answer
```
</p></details>

<!--chapter:end:posts/020-Python_BT.Rmd-->

