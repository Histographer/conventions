## Code Convention Philosophy
>  Our code convention philosophy: Code is far more read than it is written, so we will favor read-time convenience to write-time convenience. 

These conventions are based on Simon McConnell’s framework for code conventions from the book [Code Complete](https://en.wikipedia.org/wiki/Code_Complete).

## Style
TBD

## General Conventions
### Human Language
English Language when naming variables, functions, classes and comments

Use descriptive language when naming functions/variables. They should be self-explainatory.


```python
#BAD
mxpl = 7
current = datetime.datetime.now()

def date():
  return current
```

```python
#GOOD
max_people = 7
current_date = datetime.datetime.now()

def getCurrentDate():
  return current_date
```

### Computer Language
#### Javascript - camelCase
```javascript
let camelCaseVariable = "This looks good"
```
#### Json - camelCase
```json
{
"camelCaseVariable" : "This looks good"
}
```

#### Python - snake_case
``` python
snake_case_variable = "This looks good!"
```
### No Magic numbers
This is numbers directly in the functions that serve a specific value.
``` python 
# BAD
if password_length > 7:
    print("Password has to be shorter")
```
```python 
# GOOD
MAX_PASSWORD_LENGTH = 7
if password_length > MAX_PASSWORD_LENGTH:
    print("Password has to be shorter")

```


### Use Encapsulation
Never access other classes variables directly. 
```javascript
// BAD
class Person {
  constructor(name) {
    this.name = name;
  }
}

kent = new Person('kent')
kentsName = kent.name
kent.name = 'Eline'
```

```javascript
//GOOD
class Person {
  constructor(name) {
    this.name = name;
  }

  //This is encapsulation
  getName() {
    return this.name
  }

  setName(name) {
    this.name = name
  }
}

kent = new Person('kent')
kentsName = kent.getName()
kent.setName('Eline')
```

## Naming Specifics
### Constants
UPPERCASE_LETTERS with snake_case

```python
MAX_PASSWORD_LENGTH = 99
```

### Boolean 
Use positive boolean names

```python 
#BAD
notFound = true

#GOOD
found = true
```

Typical boolean names:
``` python
#To indicate whether something is done
done = true
isDone = true

#to indicate whether an error has occured
error = false
hasError = false

#to indicate whether a value has been found
found = true
isFound = true

#To indicate whether an operation has been successful
success = true
ok = false
```
