# File I/O
## txt
File I/O is the ability of a program to take a file as input or create a file as output.
### open
automate the opening of a file
```python
name = input("What's your name? ")

file = open("names.txt", "a")
file.write(f"{name}\n")
file.close()
```

### with
automate the closing of a file
```python
name = input("What's your name? ")

with open("names.txt", "a") as file:
    file.write(f"{name}\n")
```
## csv
### read
```python
import csv

students = []

with open("students.csv") as file:
    reader = csv.DictReader(file)
    for row in reader:
        students.append({"name": row["name"], "home": row["home"]})

for student in sorted(students, key=lambda student: student["name"]):
    print(f"{student['name']} is in {student['home']}")
```
### write
```python
import csv

name = input("What's your name? ")
home = input("Where's your home? ")

with open("students.csv", "a") as file:
    writer = csv.DictWriter(file, fieldnames=["name", "home"])
    writer.writerow({"name": name, "home": home})
```

## PIL for image (binary file)
```python
# create animated gif
import sys
from PIL import Image

images = []

# append the second image to the first image
for arg in sys.argv[1:]:
    image = Image.open(arg)
    images.append(image)

# save the animated gif as costumes.gif
images[0].save(
    "costumes.gif", save_all=True, append_images=[images[1]], duration=200, loop=0
)


```
