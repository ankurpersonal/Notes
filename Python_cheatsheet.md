# 🐍 Python Cheat Sheet: Loops, Strings, Roman Numerals, and More

# ================================
# 🔁 Looping Patterns

# 1. Simple for loop
for item in iterable:
    print(item)

# 2. For loop with index
for index, item in enumerate(iterable):
    print(index, item)

# 3. For loop over range
for i in range(n):
    print(i)

# 4. For loop with custom range
for i in range(start, stop, step):
    print(i)

# 5. While loop
while condition:
    print("Looping...")

# 6. Nested for loop
for i in range(3):
    for j in range(2):
        print(i, j)

# 7. Nested while loop
i = 0
while i < 3:
    j = 0
    while j < 2:
        print(i, j)
        j += 1
    i += 1

# ================================
# 🔁 Looping Over Data Structures

# 8. Loop over list
my_list = [10, 20, 30]
for item in my_list:
    print(item)

# 9. Loop over dictionary
my_dict = {'a': 1, 'b': 2}
for key, value in my_dict.items():
    print(key, value)

# 10. Loop over set
my_set = {1, 2, 3}
for item in my_set:
    print(item)

# 11. Loop over string
for char in "hello":
    print(char)

# ================================
# 🔁 Loop Control Statements

# 12. break
for i in range(5):
    if i == 3:
        break
    print(i)

# 13. continue
for i in range(5):
    if i == 3:
        continue
    print(i)

# 14. else with loop
for i in range(5):
    if i == 3:
        break
else:
    print("Completed without break")

# ================================
# 🔁 Advanced Loop Patterns

# 15. List comprehension
squares = [x*x for x in range(5)]

# 16. Loop with zip
names = ['Alice', 'Bob']
scores = [85, 90]
for name, score in zip(names, scores):
    print(name, score)

# 17. Loop with reversed
for item in reversed(my_list):
    print(item)

# 18. Loop with sorted
for item in sorted(my_list):
    print(item)

# ================================
# 🔁 String Traversal

text = "Python is fun"

# 1. Character by character
for char in text:
    print(char)

# 2. Using index
for i in range(len(text)):
    print(text[i])

# 3. Using enumerate
for i, char in enumerate(text):
    print(i, char)

# 4. Reverse traversal
for char in reversed(text):
    print(char)

# 5. Reverse with slicing
for char in text[::-1]:
    print(char)

# 6. Skip certain characters
for char in text:
    if char == 'o':
        continue
    print(char)

# 7. Break on condition
for char in text:
    if char == 'n':
        break
    print(char)

# 8. Manual index jump
i = 0
while i < len(text):
    print(text[i])
    if text[i] == 'y':
        i += 2
    else:
        i += 1

# 9. Adjacent characters
for i in range(len(text) - 1):
    print(text[i], text[i + 1])

# 10. Sliding window
for i in range(len(text) - 2):
    print(text[i:i+3])

# 11. Find vowels
vowels = "aeiou"
for char in text:
    if char in vowels:
        print("Vowel:", char)

# 12. List comprehension
uppercase = [char.upper() for char in text]

# 13. zip for parallel strings
s1 = "abc"
s2 = "123"
for c1, c2 in zip(s1, s2):
    print(c1, c2)

# 14. map
result = list(map(str.upper, text))

# ================================
# 🧵 Last Word of a Sentence

sentence = "Python is powerful and fun!"

# 1. Basic split
last_word = sentence.split()[-1]

# 2. Strip punctuation
import string
cleaned = sentence.strip(string.punctuation)
last_word = cleaned.split()[-1]

# 3. rsplit
last_word = sentence.rsplit(' ', 1)[-1]

# 4. Regex
import re
words = re.findall(r'\b\w+\b', sentence)
last_word = words[-1]


# 🐍 Python Cheat Sheet: Slice Alternatives and String Manipulation

# ============================================
# 🔁 Slice Alternatives by Scenario

# 1. Accessing a substring or sublist
text = "abcdef"
# ✅ Using slice
sub = text[2:5]  # 'cde'
# 🚫 Alternative
sub = ''.join([text[i] for i in range(2, 5)])

# 2. Reversing a string or list
# ✅ Using slice
reversed_text = text[::-1]
# 🚫 Alternative
reversed_text = ''.join(reversed(text))
# For lists:
my_list = [1, 2, 3]
reversed_list = list(reversed(my_list))

# 3. Copying a list or string
# ✅ Using slice
copy = my_list[:]
# 🚫 Alternative
copy = list(my_list)
copy = my_list.copy()

# 4. Getting first N elements
n = 3
# ✅ Using slice
first_n = my_list[:n]
# 🚫 Alternative
first_n = [my_list[i] for i in range(n)]

# 5. Getting last N elements
# ✅ Using slice
last_n = my_list[-n:]
# 🚫 Alternative
last_n = [my_list[i] for i in range(len(my_list) - n, len(my_list))]

# 6. Skipping elements (step slicing)
# ✅ Using slice
skipped = my_list[::2]
# 🚫 Alternative
skipped = [my_list[i] for i in range(0, len(my_list), 2)]

# 7. Removing first or last character from string
# ✅ Using slice
trimmed = text[1:-1]
# 🚫 Alternative
trimmed = ''.join([text[i] for i in range(1, len(text) - 1)])

# 8. Splitting and extracting last word
sentence = "Python is powerful and fun!"
# ✅ Using split and slice
last_word = sentence.split()[-1]
# 🚫 Alternative
words = []
word = ''
for char in sentence:
    if char == ' ':
        if word:
            words.append(word)
            word = ''
    else:
        word += char
if word:
    words.append(word)
last_word = words[-1]

# ============================================
# 🧠 Pro Tips
# - Use range(start, stop, step) for manual control.
# - Use reversed(), copy(), and join() as clean alternatives.
# - Avoid slicing in performance-critical or restricted environments by using loops and comprehensions.


# ================================
# 🔢 Roman to Integer

def romanToInt(s: str) -> int:
    roman = {'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000}
    total = 0
    prev = 0
    for char in reversed(s):
        value = roman[char]
        if value < prev:
            total -= value
        else:
            total += value
        prev = value
    return total

# ================================
# 🔢 Integer to Roman

def intToRoman(num: int) -> str:
    val_map = [
        (1000, "M"), (900, "CM"), (500, "D"), (400, "CD"),
        (100, "C"), (90, "XC"), (50, "L"), (40, "XL"),
        (10, "X"), (9, "IX"), (5, "V"), (4, "IV"), (1, "I")
    ]
    result = []
    for value, symbol in val_map:
        count = num // value
        result.append(symbol * count)
        num %= value
    return ''.join(result)
