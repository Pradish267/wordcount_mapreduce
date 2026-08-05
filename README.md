# Exp 02 Word Count using MapReduce

**Date:**5.8.2026

## AIM:
To implement the Word Count program using the MapReduce programming model and determine the frequency of each word in the given input text.

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create a Python/Java project in the preferred IDE (Eclipse/IntelliJ IDEA/VS Code).

### Step 3:
Create the Python/Java program for the Word Count application using the MapReduce concept.

### Step 4:
Implement the **Mapper** phase to read the input text and emit each word as a key with a value.

### Step 5:
Implement the **Shuffle and Sort** phase to group identical words together.

### Step 6:
Implement the **Reducer** phase to sum the values associated with each word and calculate its total frequency.

### Step 7:
Compile and execute the program.

### Step 8:
Verify and display the word frequencies.

## PROGRAM:

*(Paste the Java code for the Word Count MapReduce program here.)*
```
from collections import defaultdict
text = input("Enter the text: ")
def mapper(text):
    mapped = []
    words = text.lower().split()

    for word in words:
        mapped.append((word, 1))

    return mapped
def reducer(mapped_data):
    result = defaultdict(int)

    for key, value in mapped_data:
        result[key] += value

    return result
mapped = mapper(text)
reduced = reducer(mapped)
print("\nMapped Output:")
for item in mapped:
    print(item)
print("\nWord Frequencies:")
for word in sorted(reduced):
    print(f"{word}: {reduced[word]}")
    
```
## OUTPUT:

*(Paste the execution output showing the frequency of each word here.)*
<img width="828" height="421" alt="exp2big" src="https://github.com/user-attachments/assets/62c2fd22-591b-4e7f-8c62-cbca94d0bddc" />

## RESULT:

The Word Count program using the MapReduce programming model was implemented successfully, and the frequency of each word in the given input text was computed correctly.
```
