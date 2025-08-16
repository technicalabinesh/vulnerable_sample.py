# vulnerable_sample.py

import os
import sqlite3

# 1. Hardcoded secret (bad practice)
API_KEY = "123456789SECRET"

# 2. Using eval on user input (code injection)
user_input = input("Enter Python expression: ")
result = eval(user_input)
print(f"Result: {result}")

# 3. Command injection
filename = input("Enter file name to list: ")
os.system(f"ls {filename}")

# 4. SQL injection
conn = sqlite3.connect("users.db")
cursor = conn.cursor()
username = input("Enter username to search: ")
query = f"SELECT * FROM users WHERE username='{username}'"
cursor.execute(query)
rows = cursor.fetchall()
print(rows)

# 5. Insecure deserialization
import pickle
data = input("Enter pickled object: ")
obj = pickle.loads(data.encode())

# 6. Weak random password
import random
password = random.randint(1000, 9999)
print(f"Generated weak password: {password}")
