# PEP 8 - Python Enhancement Proposal 8
- Ref https://peps.python.org/pep-0008/


### 001.Không sử dụng tab để thụt lề, hãy sử dụng 4 dấu cách (spaces).
Ví dụ:
```python
if x == 1:  
    print("x is 1") 
``` 

### 002.Sử dụng khoảng trắng đúng cách để cải thiện khả năng đọc của mã.
Ví dụ:
```python
total = variable1 + (variable2 * 5) - variable3
```

### 003.Sử dụng quy tắc snake_case để đặt tên biến, có nghĩa là sử dụng chữ thường và dấu gạch dưới (_) thay vì khoảng trắng hoặc chữ hoa.
Ví dụ:
```python
my_variable_name = 5
```

### 004.Đặt positional arguments trước keyword arguments:

Khi định nghĩa hàm, tham số vị trí (positional arguments) phải được đặt trước tham số từ khóa (keyword arguments).
Ví dụ:
```python
def function_name(arg1, arg2, kwarg1=None, kwarg2=None):  
    pass
```

### 005.Đặt tên biến hằng bằng chữ in hoa và sử dụng dấu gạch dưới (_) để phân tách các từ.
Ví dụ:
```python
MAX_VALUE = 100
```

### 006.Shebang line là dòng đầu tiên trong một tập tin script, bắt đầu bằng #!, dùng để chỉ định trình thông dịch nào sẽ thực thi tập tin đó.
Ví dụ:
```python
#!/usr/bin/env python
``` 
Trong ví dụ trên, dòng này cho biết hệ điều hành nên sử dụng trình thông dịch Python để chạy script. Điều này giúp script có thể chạy trực tiếp từ dòng lệnh mà không cần nhập lệnh python trước tên tập tin.

### 007.Docstrings:
Docstring là chuỗi văn bản nằm ngay bên dưới định nghĩa hàm, được sử dụng để mô tả chức năng, các tham số và giá trị trả về của hàm.
Ví dụ:
```python
def my_function(param1, param2):  
    """  
    This is a docstring that explains the function.  
    
    Parameters:  
    param1 (int): Description of param1.  
    param2 (str): Description of param2.  
    
    Returns:  
    bool: The return value.  
    """  
    pass 
```

### 008.Sử dụng CapWords cho tên lớp:
Khi đặt tên cho lớp trong Python, sử dụng quy tắc CapWords (hay còn gọi là CamelCase), tức là bắt đầu mỗi từ trong tên lớp bằng chữ hoa và không dùng dấu gạch dưới.
Ví dụ:
```python
class LopCuaToi:  
    pass
```

### 009.Tránh sử dụng danh sách là đối số mặc định
Khi định nghĩa hàm, tránh sử dụng danh sách (hoặc các đối tượng thay đổi khác) làm đối số mặc định, vì nó có thể dẫn đến hành vi không mong muốn.

Thay vào đó, hãy kiểm tra xem đối số có phải là None hay không và gán một danh sách mới bên trong hàm.

Ví dụ sai
```python
def them_phan_vao_danh_sach(danh_sach=[]):  
    danh_sach.append(1)  
    return danh_sach
``` 

Để tránh vấn đề này, bạn nên sử dụng None làm đối số mặc định như sau:
```python
def them_phan_vao_danh_sach(danh_sach=None):  
    if danh_sach is None:  
        danh_sach = []  
    danh_sach.append(1)  
    return danh_sach
```

### 010.Sử dụng dòng trống để phân tách hàm và lớp trong Python là một cách để cải thiện khả năng đọc của mã nguồn. Bằng cách thêm dòng trống giữa các hàm hoặc lớp, bạn giúp người đọc dễ dàng nhận ra các phần khác nhau của mã.

Ví dụ:
```python
def ham1():  
    pass  

def ham2():  
    pass  
```

### 011.Dấu ngoặc:
Sử dụng dấu ngoặc cho các điều kiện phức tạp để tăng tính rõ ràng.
```python
if (x > 0 and   
    y < 10):  
    pass
```

### 012.Sắp xếp import:
Sắp xếp các import theo thứ tự từ thư viện chuẩn, thư viện bên ngoài, và thư viện nội bộ.
```python
import os  
import sys  

from mymodule import myfunction  
```

### 013.Chú thích dòng:
Chú thích nên được viết trên cùng một dòng với mã, với ít nhất 2 khoảng trắng.
```python
x = x + 1  # Tăng giá trị x lên 1

```

### 014.Tránh sử dụng dấu cách trong biểu thức điều kiện
```python
if x in range(10):  
    print("x là một số trong khoảng 0 đến 9.")  
Giải thích: Không nên có dấu cách giữa chức năng và dấu ngoặc đơn.
```

### 015.Ký hiệu 'self' và 'cls':
Sử dụng 'self' cho tham số đầu tiên của phương thức trong lớp, và 'cls' cho phương thức lớp.
```python
class MyClass:
    def my_method(self):  
        pass

```

### 016.Sử dụng with để tự động đóng file
```python
try:  
    with open('example.txt', 'r') as file:  
        content = file.read()  
except FileNotFoundError:  
    print("File not found.")  
except IOError as e:  
    print(f"An error occurred: {e}")
```
Giải thích: Sử dụng with tự động đóng file khi kết thúc khối lệnh.

#### Kiểm tra xem file có tồn tại hay không trước khi mở
```python
import os  

filename = 'example.txt'  
if os.path.exists(filename):  
    with open(filename, 'r') as file:  
        content = file.read()  
else:  
    print("File does not exist.")
```
Giải thích: Kiểm tra sự tồn tại của file trước khi mở nhằm tránh lỗi.

#### Đọc file dòng theo dòng
```python
try:  
    with open('example.txt', 'r') as file:  
        for line in file:  
            print(line.strip())  
except FileNotFoundError:  
    print("File not found.")
```
Giải thích: Đọc file từng dòng để tiết kiệm bộ nhớ cho file lớn.

#### Ghi vào file mới
```python
try:  
    with open('new_file.txt', 'w') as file:  
        file.write("Hello, World!")  
except IOError as e:  
    print(f"An error occurred: {e}")  
```python
Giải thích: Mở file ở chế độ ghi, tạo file mới nếu chưa tồn tại.

#### Ghi thêm vào file đã tồn tại
```python
try:  
    with open('existing_file.txt', 'a') as file:  
        file.write("Appending this line.\n")  
except IOError as e:  
    print(f"An error occurred: {e}")  
```
Giải thích: Dùng chế độ thêm (append) để không ghi đè lên nội dung cũ.

#### Đọc từng byte từ file
```python
try:  
    with open('example.txt', 'rb') as file:  
        byte = file.read(1)  
        while byte:  
            print(byte)  
            byte = file.read(1)  
except FileNotFoundError:  
    print("File not found.")  
```
Giải thích: Đọc file theo byte, hữu ích với các file nhị phân.

#### Đọc một file nhị phân
```python
try:  
    with open('image.png', 'rb') as file:  
        content = file.read()  
except FileNotFoundError:  
    print("File not found.")  
```
Giải thích: Mở file nhị phân để xử lý hình ảnh hoặc file không văn bản.

#### Ghi nhiều dòng vào file
```python
lines = ["Line 1\n", "Line 2\n", "Line 3\n"]  
try:  
    with open('lines.txt', 'w') as file:  
        file.writelines(lines)  
except IOError as e:  
    print(f"An error occurred: {e}")  
```
Giải thích: Sử dụng writelines() để ghi nhiều dòng cùng lúc.

#### Thay đổi encoding khi mở file
```python
try:  
    with open('example.txt', 'r', encoding='utf-8') as file:  
        content = file.read()  
except UnicodeDecodeError:  
    print("Encoding error occurred.")  
```
Giải thích: Chỉ định encoding khi mở file có thể tránh được lỗi mã hóa.

#### Đổ dữ liệu ra file JSON
```python
import json  

data = {'name': 'John', 'age': 30}  
try:  
    with open('data.json', 'w') as file:  
        json.dump(data, file)  
except IOError as e:  
    print(f"An error occurred: {e}")  
```
Giải thích: Sử dụng json.dump() để ghi đối tượng Python sang file JSON.

#### Đọc dữ liệu từ file JSON
```python
try:  
    with open('data.json', 'r') as file:  
        data = json.load(file)  
except FileNotFoundError:  
    print("File not found.")  
```
Giải thích: Sử dụng json.load() để đọc dữ liệu từ file JSON.

#### Xử lý lỗi phân tích cú pháp
```python
try:  
    with open('data.json', 'r') as file:  
        data = json.load(file)  
except json.JSONDecodeError:  
    print("JSON decode error.")  
```
Giải thích: Kiểm soát lỗi khi dữ liệu trong file JSON không hợp lệ.

#### Xử lý lỗi quyền truy cập
```python
try:  
    with open('protected_file.txt', 'r') as file:  
        content = file.read()  
except PermissionError:  
    print("Permission denied.")  
```
Giải thích: Kiểm soát lỗi khi không có quyền truy cập vào file.

#### Đọc file lớn theo khối (chunk)
```python
try:  
    with open('large_file.txt', 'r') as file:  
        while chunk := file.read(1024):  # Đọc 1024 byte mỗi lần  
            print(chunk)  
except FileNotFoundError:  
    print("File not found.")  
```
Giải thích: Đọc file lớn theo khối để tiết kiệm bộ nhớ.

#### Đếm số dòng trong file
```python
try:  
    with open('example.txt', 'r') as file:  
        line_count = sum(1 for line in file)  
    print(f"Total lines: {line_count}")  
except FileNotFoundError:  
    print("File not found.")  
```
Giải thích: Đếm số dòng trong file bằng comprehension.

#### Kiểm tra kiểu file dựa trên extension
```python
import os  

filename = 'example.txt'  
if os.path.splitext(filename)[1] == '.txt':  
    try:  
        with open(filename, 'r') as file:  
            content = file.read()  
    except FileNotFoundError:  
        print("File not found.")  
```
Giải thích: Kiểm tra phần mở rộng file trước khi mở.

#### Tạo và ghi file CSV
```python
import csv  

data = [["Name", "Age"], ["John", 30], ["Jane", 25]]  
try:  
    with open('people.csv', 'w', newline='') as file:  
        writer = csv.writer(file)  
        writer.writerows(data)  
except IOError as e:  
    print(f"An error occurred: {e}")  
```
Giải thích: Ghi dữ liệu vào file CSV.

#### Đọc file CSV
```python
try:  
    with open('people.csv', 'r') as file:  
        reader = csv.reader(file)  
        for row in reader:  
            print(row)  
except FileNotFoundError:  
    print("File not found.")  
```
Giải thích: Đọc file CSV và xử lý từng dòng.

#### Nén file với gzip
```python
import gzip  

try:  
    with open('example.txt', 'rb') as file:  
        with gzip.open('example.txt.gz', 'wb') as out_file:  
            out_file.writelines(file)  
except IOError as e:  
    print(f"An error occurred: {e}")  
```
Giải thích: Nén file với gzip để tiết kiệm không gian lưu trữ.

#### Giải nén file gzip
```python
import gzip  

try:  
    with gzip.open('example.txt.gz', 'rb') as file:  
        content = file.read()  
except FileNotFoundError:  
    print("File not found.")  
```
Giải thích: Mở file nén với gzip để truy cập nội dung.


### 017.Type hints cho các hàm
```python
def concatenate_strings(s1: str, s2: str) -> str:  
    return s1 + s2  
```
Giải thích: Sử dụng type hints để chỉ định kiểu dữ liệu của tham số và giá trị trả về, giúp dễ dàng kiểm tra và tài liệu hóa mã của bạn.

### 018.Tối ưu hóa import:
Chỉ import những gì cần thiết để tránh việc import toàn bộ module.
```python
from math import pi
```

### 019.Sử dụng đa dòng:
Khi một chuỗi quá dài, sử dụng dấu ngoặc đơn hoặc ngoặc vuông cho chuỗi đa dòng.
```python
my_string = (  
    "Đây là một chuỗi quá dài "  
    "và cần phải chia ra thành nhiều dòng."  
)
```

### 020.Xử lý ngoại lệ:
```python
try:
    file = open('example.txt', 'r')
    content = file.read()
    file.close()
except FileNotFoundError:
    print("File not found.")
except IOError as e:
    print(f"An error occurred: {e}")
except Exception as e:
    print(f"An unexpected error occurred: {e}")
finally:
    print("Execution completed.")
```

### 021.Sử dụng list comprehension
```python
squares = [x**2 for x in range(10)]
```
Giải thích: Sử dụng list comprehension để tạo danh sách bình phương của các số từ 0 đến 9 một cách ngắn gọn và rõ ràng.


### 022.Khai báo biến nhóm
```python
first_name, last_name = "John", "Doe"
```
Giải thích: Khai báo biến nhóm giúp mã gọn gàng hơn.


### 023.Sử dụng enumerate khi duyệt qua danh sách
```python
for index, value in enumerate(my_list):  
    print(index, value)  
```
Giải thích: Sử dụng enumerate để có cả chỉ số và giá trị khi duyệt qua danh sách.


### 024.Kiểm tra None bằng cách so sánh trực tiếp
```python
if my_variable is not None:  
    print("Variable có giá trị")  
```
Giải thích: Sử dụng is not None là cách tốt hơn để kiểm tra giá trị None


### 026. Sử dụng set để loại bỏ trùng lặp
```python
unique_numbers = set([1, 2, 2, 3, 4])  
```
Giải thích: Sử dụng set để tạo ra danh sách không có phần tử trùng lặp.


### 027.Định nghĩa biến toàn cục trong nội bộ hàm với global
```python
count = 0  
def increment():  
    global count  
    count += 1
```
### 028.Khởi tạo list
numbers = [0] * 10  # Khởi tạo danh sách có kích thước 10


### 029.Sử dụng extend() thay vì append() để thêm nhiều phần tử:
```python
list1 = [1, 2, 3]  
list1.extend([4, 5])  # Thêm nhiều phần tử
```

### 030.Sử dụng .get() để truy cập giá trị: Điều này giúp tránh KeyError nếu khóa không tồn tại.
```python
value = my_dict.get('key', default_value)  # Sử dụng get
```

### 031.Sử dụng collections.defaultdict cho từ điển với giá trị mặc định: Khi bạn cần tự động khởi tạo các giá trị.
```python
from collections import defaultdict  
my_dict = defaultdict(int)  # Mặc định là 0
```

### 032.Sử dụng is để so sánh với None
```python
Sai

if x == None:  
    print("x is None")  
Đúng

if x is None:  
    print("x is None") 
```

### 033.Tránh sử dụng số ma thuật
```python
Sai

price = 100  
discounted_price = price * 0.9  
Đúng

PRICE = 100  
DISCOUNT_RATE = 0.9  
discounted_price = PRICE * DISCOUNT_RATE
```

### 034.Sử dụng assert cho kiểm tra
```python
Sai

def divide(a, b):  
    if b == 0:  
        raise ValueError("Cannot divide by zero")  
    return a / b  
Đúng

def divide(a, b):  
    assert b != 0, "Cannot divide by zero"  
    return a / b 

 ```
### 035.Ưu tiên sử dụng f-string cho định dạng chuỗi
```python
Sai

name = "John"  
greeting = "Hello, " + name + "!"  
Đúng

name = "John"  
greeting = f"Hello, {name}!"
```

### 036.Sử dụng sorted thay vì sort để không thay đổi danh sách gốc
```python
Sai

my_list = [3, 1, 2]  
my_list.sort()  
Đúng

my_list = [3, 1, 2]  
sorted_list = sorted(my_list)
```

### 037.Sử dụng zip cho việc kết hợp các danh sách
```python
Sai

names = ["Alice", "Bob"]  
ages = [25, 30]  
for i in range(len(names)):  
    print(names[i], ages[i])  
Đúng

names = ["Alice", "Bob"]  
ages = [25, 30]  
for name, age in zip(names, ages):  
    print(name, age)

```

### 038.Tránh sữa đổi các đối tượng mutable bên trong hàm
```python
Sai

def add_item(my_list):  
    my_list.append(1)  

items = []  
add_item(items)  
Đúng

def add_item(my_list):  
    new_list = my_list.copy()  
    new_list.append(1)  
    return new_list  

items = []  
new_items = add_item(items)
```

### 039.Sử dụng hàm join để nối chuỗi
```python
Sai

my_list = ["a", "b", "c"]  
result = ""  
for item in my_list:  
    result += item  
Đúng

my_list = ["a", "b", "c"]  
result = "".join(my_list)
```

### 040.Sử dụng isinstance để kiểm tra loại
```python
Sai

if type(x) == int:  
    print("x is an int")  
Đúng

if isinstance(x, int):  
    print("x is an int")
```

### 041.Sử dụng Counter để đếm tần suất
```python
Sai

letters = ["a", "b", "a", "c"]  
counts = {}  
for letter in letters:  
    if letter in counts:  
        counts[letter] += 1  
    else:  
        counts[letter] = 1  
Đúng

from collections import Counter  

letters = ["a", "b", "a", "c"]  
counts = Counter(letters)  
```

### 042.Sử dụng kiểu dữ liệu số hợp lý
```python
Sai

a = 0.1 + 0.2  # Kết quả không như mong đợi  
Đúng

from decimal import Decimal  

a = Decimal('0.1') + Decimal('0.2') 

```

### 043.Sử dụng *args và **kwargs trong hàm
```python
Sai
def my_function(arg1, arg2):  
    pass  
Đúng
def my_function(*args, **kwargs):  
    pass
```

### 044.Sử dụng kiểm tra kiểu để tránh lỗi
```python
Sai

def add(a, b):  
    return a + b  
Đúng

def add(a, b):  
    if isinstance(a, (int, float)) and isinstance(b, (int, float)):  
        return a + b  
    raise ValueError("Both arguments must be numbers.")

```

### 045.Sử dụng shuffle từ module random
```python
Sai

import random  
items = [1, 2, 3, 4, 5]  
for i in range(len(items)):  
    j = random.randint(0, len(items) - 1)  
    items[i], items[j] = items[j], items[i]  
Đúng

import random  

items = [1, 2, 3, 4, 5]  
random.shuffle(items)
```

### 046.Sử dụng kiểu dữ liệu chính xác trong lớp
```python
Sai

class Person:  
    def __init__(self, name, age):  
        self.name = name  
        self.age = age  
Đúng

class Person:  
    def __init__(self, name: str, age: int):  
        self.name = name  
        self.age = age
```

### 047.Sử dụng all() và any() để kiểm tra điều kiện
```python
Sai

all_positive = True  
for x in numbers:  
    if x <= 0:  
        all_positive = False  
Đúng

all_positive = all(x > 0 for x in numbers)
```
```python
### 048.Sử dụng raise để tạo ngoại lệ

Sai

def divide(a, b):  
    if b == 0:  
        return "Cannot divide by zero"  
Đúng

def divide(a, b):  
    if b == 0:  
        raise ValueError("Cannot divide by zero")  
    return a / b
```
### 048. Tham số vị trí và tham số keyword:
Lời gọi bằng tham số vị trí
Nếu bạn định nghĩa một phương thức có tham số kiểu keyword, bạn có thể gọi nó bằng cách truyền các tham số theo thứ tự vị trí, miễn là bạn đã cung cấp đủ số lượng tham số cần thiết. Dưới đây là một số ví dụ minh họa:

Ví dụ:
class MyClass:  
    def my_method(self, a, b, c=10):  
        return a + b + c  

# Gọi bằng tham số vị trí  
result1 = MyClass().my_method(5, 3)  # c sẽ nhận giá trị mặc định là 10  
print(result1)  # Kết quả: 18  

# Gọi bằng tham số vị trí với tham số thứ ba  
result2 = MyClass().my_method(5, 3, 4)  # c sẽ là 4  
print(result2)  # Kết quả: 12  

# Lời gọi bằng tham số kiểu keyword  
result3 = MyClass().my_method(a=5, b=3)  
print(result3)  # Kết quả: 18  
Gọi bằng tham số trộn lẫn
Bạn cũng có thể kết hợp cả hai cách gọi: tham số vị trí và tham số kiểu keyword. Tuy nhiên, các tham số vị trí phải được đặt trước tiên trước khi sử dụng tham số kiểu keyword.

result4 = MyClass().my_method(5, b=3)  # a là 5, b là 3, c là 10  
print(result4)  # Kết quả: 18  
Nếu bạn cố gắng truyền tham số theo thứ tự vị trí cho một tham số đã được xác định là kiểu keyword bên dưới, bạn sẽ nhận được lỗi.

# Ví dụ sai  
try:  
    result5 = MyClass().my_method(a=5, 3)  # Lỗi  
except SyntaxError as e:  
    print(e)  # Sẽ in ra lỗi cú pháp  

