# <p align = "center">JsonListdata
<p align = "center">JsonListdata is easy instrument for read and write json file

## Getting started
* Installation from source
```
$ git clone https://github.com/DENLID/JLdata.git
```
## Content
* [Getting started](#getting-started)
* [First steps](#firsts-steps)
  * [Edit data](#edit-data)
  * [Find cell](#find-cell)
## Firsts steps
### Edit data
The JLD class enables us to interact with the file.
In argument `file` you can set your json file.
```
from JLdata import JLD
import JLdata as JL

db = JLD(file="db.json")
```
To get data write this.
```
data = db.data
```
We can create/edit in data whereupon commit changes.
```
data["name"] = "Denis"
db.commit()
```
### Find cell
To find cell by name or your key in data base use the method find_cell()
In first argument specify data. In sencond arg key which will searched cell. In third arg content in key.
```
''' Example file
{
  "name": [
    {
    "name": "Bob"
    "age": "18"
    },
    {
    "name": "Ilya"
    "age": "20"
    }
  ]
}
'''

user = JL.find_cell(db, "name", "Bob")
print(user["age"]) # 18

user = JL.find_cell(db, "name", "Ilya")
print(user["age"]) # 20

user = JL.find_cell(db, "name", "Denis")
print(user["age"]) # None
```
