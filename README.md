# 🔁 Python Looping Cheat Sheet

# -------------------------------
# 1. Simple for loop
for item in iterable:
    print(item)

# 2. For loop with index
for index, item in enumerate(iterable):
    print(index, item)

# 3. For loop over range
for i in range(n):  # 0 to n-1
    print(i)

# 4. For loop with custom range
for i in range(start, stop, step):
    print(i)

# 5. While loop
while condition:
    print("Looping...")

# -------------------------------
# 🔁 Nested Loops

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

# -------------------------------
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

# -------------------------------
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

# -------------------------------
# 🔁 Advanced Patterns

# 15. List comprehension
squares = [x*x for x in range(5)]

# 16. Loop with zip (parallel iteration)
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

# -------------------------------
# 🧠 Pro Tips
# - Prefer for over while when possible — it's cleaner and safer.
# - Use enumerate() for index access.
# - Use zip() for parallel iteration.
# - Use comprehensions for concise transformations.
