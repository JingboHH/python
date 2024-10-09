# python
## List Comprehensions
```py
if __name__ == '__main__':
    x = int(input())
    y = int(input())
    z = int(input())
    n = int(input())
    
    array = [[i, j, k]
    for i in range (x + 1)
        for j in range (y + 1)
            for k in range (z + 1)
                if i + j + k != n]
    print(array)
```
## Find the Runner-Up Score!
```py
if __name__ == '__main__':
    n = int(input())
    arr = list(map(int, input().split()))
    a = max(arr)
    while a in arr:
        arr.remove(a)
    print(max(arr))
```
## Nested Lists
```py
if __name__ == '__main__':
    students = []
    for _ in range(int(input())):
        name = input()
        score = float(input())
        students.append([name, score])
    scores = {i[1] for i in students}
    scores.remove(min(scores))
    result = [i[0] for i in students if i[1]==min(scores)]

    for i in sorted(result):
        print(i)
```
## Finding the percentage
```py
if __name__ == '__main__':
    n = int(input())
    student_marks = {}
    for _ in range(n):
        name, *line = input().split()
        scores = list(map(float, line))
        student_marks[name] = scores
    query_name = input()
    res = sum(student_marks[query_name]) / 3
print(f"{res:.2f}")
```
## Lists
```py
if __name__ == '__main__':
    N = int(input())
    output = []
    for _ in range(N):
        inputs = input().split()
        if inputs[0] == "insert":
            output.insert(int(inputs[1]), int(inputs[2]))
        elif inputs[0] == "print":
            print(output)
        elif inputs[0] == "remove":
            output.remove(int(inputs[1]))
        elif inputs[0] == "append":
            output.append(int(inputs[1]))
        elif inputs[0] == "sort":
            output.sort()
        elif inputs[0] == "pop":
            output.pop()
        elif inputs[0] == "reverse":
            output.reverse()  
            
    operations = {
        ""
    }
```
## Tuples
```py
if __name__ == '__main__':
    n = int(input())
    elements = tuple(map(int, input().split())) 
    print(hash(elements))
```
## Find the Torsional Angle
```py
class Points(object):
    def __init__(self, x, y, z):
        self.x = x
        self.y = y
        self.z = z

    def __sub__(self, other):
        return Points(self.x - other.x, self.y - other.y, self.z - other.z)

    def dot(self, other):
        return self.x * other.x + self.y * other.y + self.z * other.z

    def cross(self, other):
        return Points(
            self.y * other.z - self.z * other.y,
            self.z * other.x - self.x * other.z,
            self.x * other.y - self.y * other.x
        )
        
    def absolute(self):
        return pow((self.x ** 2 + self.y ** 2 + self.z ** 2), 0.5)
```

## sWAP cASE
```py
def swap_case(s):
    return s.swapcase()

if __name__ == '__main__':
    s = input()
    result = swap_case(s)
    print(result)

# String Split and Join

def split_and_join(line):
    # write your code here
    return "-".join(line.split())
if __name__ == '__main__':
    line = input()
    result = split_and_join(line)
    print(result)
```

## What's Your Name?
```py
#
# Complete the 'print_full_name' function below.
#
# The function is expected to return a STRING.
# The function accepts following parameters:
#  1. STRING first
#  2. STRING last
#

def print_full_name(first, last):
    # Write your code here
    print(f"Hello {first} {last}! You just delved into python. ")
if __name__ == '__main__':
    first_name = input()
    last_name = input()
    print_full_name(first_name, last_name)
```

## Mutations
```py

def mutate_string(string, position, character):
    list_format = list(string)
    list_format[position]= character
    string = ''.join(list_format)

    return string

if __name__ == '__main__':
    s = input()
    i, c = input().split()
    s_new = mutate_string(s, int(i), c)
    print(s_new)
```
## Find a string
```py
def count_substring(string, sub_string):
    count = 0
    k = len(sub_string)
    for i in range(0, len(string)):
        if sub_string in string[i: i+k]:
            count += 1
    return count

if __name__ == '__main__':
    string = input().strip()
    sub_string = input().strip()
    
    count = count_substring(string, sub_string)
    print(count)
```
## String Validators
```py
if __name__ == '__main__':
    s = input()
    
check = [False]*5
for i in s:
    if i.isalnum():
        check[0] = True
    if i.isalpha():
        check[1] = True
    if i.isdigit():
        check[2] = True
    if i.islower():
        check[3] = True
    if i.isupper():
        check[4] = True

[print(x) for x in check]
```
## Text Alignment
```py
#Replace all ______ with rjust, ljust or center. 

thickness = int(input()) #This must be an odd number
c = 'H'

#Top Cone
for i in range(thickness):
    print((c*i).rjust(thickness-1)+c+(c*i).ljust(thickness-1))

#Top Pillars
for i in range(thickness+1):
    print((c*thickness).center(thickness*2)+(c*thickness).center(thickness*6))

#Middle Belt
for i in range((thickness+1)//2):
    print((c*thickness*5).center(thickness*6))

#Bottom Pillars
for i in range(thickness+1):
    print((c*thickness).center(thickness*2)+(c*thickness).center(thickness*6))    

#Bottom Cone
for i in range(thickness):
    print(((c*(thickness-i-1)).rjust(thickness)+c+(c*(thickness-i-1)).ljust(thickness)).rjust(thickness*6))
```
## Text Wrap
```py
import textwrap

def wrap(string, max_width):
    i= 1
    string_new = []
    for str in string:
        string_new.append(str)
        if i % max_width == 0:
            string_new.append('\n')
        i +=1
    return ''.join(string_new)

if __name__ == '__main__':
    string, max_width = input(), int(input())
    result = wrap(string, max_width)
    print(result)

# Designer Door Mat

# Enter your code here. Read input from STDIN. Print output to STDOUT

n,m=map(int,input().split())

i=0
for i in range(n):
    if i<((n-1)/2):
        print((("."+"|"+".")*(2*i+1)).center(m,"-"))
    
    elif i==((n-1)/2):
        print("WELCOME".center(m,"-"))
        
    else:
        print((("."+"|"+".")*(2*((n-1)-i)+1)).center(m,"-"))
```
## String Formatting
```py
def print_formatted(number):
    # your code goes here
    width = len(bin(number)) - 2
    for i in range(1, number + 1):
        print(f"{i:{width}d} {i:{width}o} {i:{width}X} {i:{width}b}")

if __name__ == '__main__':
    n = int(input())
    print_formatted(n)
```
## Alphabet Rangoli
```py
def print_rangoli(size):
    # your code goes here
    for i in range(-size+1, size):
        line = ''
        for j in range(abs(i), size):
            ch = chr(ord('a') + abs(j))
            if j == abs(i):
                line = ch 
            else:
                line = ch + '-' + line + '-' + ch
        print(line.center(1 + 4 * (size - 1), '-'))

if __name__ == '__main__':
    n = int(input())
    print_rangoli(n)
```
## Capitalize!
```py
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the solve function below.
def solve(s):
    s = s.split(' ')
    for i in range(len(s)):
        s[i] = s[i].capitalize()
    return ' '.join(s)
    
if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    result = solve(s)

    fptr.write(result + '\n')

    fptr.close()
```
