JSON file
================
Wei-Ming, Jiang.
May 5, 2023

- <a href="#what-is-a-json-file" id="toc-what-is-a-json-file">What is a
  JSON file?</a>
- <a href="#what-does-a-json-file-look-like"
  id="toc-what-does-a-json-file-look-like">What does a JSON file look
  like?</a>
- <a href="#read-json-file-in-python"
  id="toc-read-json-file-in-python">Read JSON file in python</a>
- <a href="#replace-null-or-na" id="toc-replace-null-or-na">Replace null
  or NA</a>
- <a href="#reference" id="toc-reference">Reference</a>

## What is a JSON file?

JSON stands for **J**ava**S**cript **O**bject **N**otation.

JSON format is an open standard file `(.json)`.

JSON is a **text format** for storing data in key-value pairs and
arrays.

- Data is in key/value pairs.

- Data is separated by commas.

- Curly braces `{}` hold objects.

- Square brackets `[]` hold arrays.

All keys must be strings written with double quotes `""`, and values
must be a valid JSON data type:

- String

- Number

- Object

- Array

- Boolean

- Null

## What does a JSON file look like?

### String

Any string value must always use double-quotes.

`{"name":"John"}`

### Number

Number values must be an integer or floating-point numbers.

`{"age":30}`

### Object

Curly braces are used to contain the object information.

`{"employee":{"name":"John", "age":30, "city":"New York"}}`

### Array

Square brackets are used to contain the array information.

`{"employees":["John", 30, "Peter"]}`

### Boolean

Boolean values are used when the data is true or false

`{"sale":true}`

### Null

The null identifies a key that has not yet been assigned a value but is
also not empty.

`{"middlename":null}`

## Read JSON file in python

``` python
import json
fileObject = open("data.json", "r", encoding="utf-8")
jsonContent = fileObject.read()
List = json.loads(jsonContent)
print(List)
```

    ## [{'number_ID': 1, 'ASSAY_VALUE': '細菌報告', 'Group': 4}, {'number_ID': 2, 'ASSAY_VALUE': '檢體null', 'Group': 5}, {'number_ID': 3, 'ASSAY_VALUE': '菌株代碼NA', 'Group': 6}]

``` python
print(List[0])
```

    ## {'number_ID': 1, 'ASSAY_VALUE': '細菌報告', 'Group': 4}

``` python
print(List[0]['ASSAY_VALUE'])
```

    ## 細菌報告

## Replace null or NA

``` python
string1 = List[1]['ASSAY_VALUE']
print(string1)
```

    ## 檢體null

``` python
print(string1.replace("null", "無"))
```

    ## 檢體無

``` python
string2 = List[2]['ASSAY_VALUE']
print(string2)
```

    ## 菌株代碼NA

``` python
print(string2.replace("NA", "無"))
```

    ## 菌株代碼無

## Reference

1.  <https://blog.hubspot.com/website/json-files>
2.  <https://pythonexamples.org/python-read-json-file/>
3.  <https://www.geeksforgeeks.org/python-string-replace/>
