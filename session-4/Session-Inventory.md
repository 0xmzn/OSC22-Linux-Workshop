## Variables

varname -> refers to the variable.

$varname -> refers to the value of the variable.


|  Assign a value to a variable | 
| --- | 
| varname="text with spaces"
  varname='text with spaces without any processing'
  varname=textwithoutspaces
  varname=20
  varname=text\ with\ spaces | 
  
 ## Taking Input from users 
  |read|$n|
  | --- | --- |
  |Ask the user for input and save it into a variable | Taking input from Command line arguments|
  
 ## Command Substitution
  $(...)
  ```
  $ thedate=$(date)
  $ echo $thedate
    Mon Feb 14 07:27:34 PM EET 2022
  ```
 ## Special Variable Types 
  |Variable |Description|
  | --- | --- |
  |BASH_VERSION |Bash version |
  | HOST_NAME| Host name |
  | HOME| Home directory |
  |PATH | Executable locations|
  |TERM | Default terminal|
  |SHELL  | Default shell|
  |EDITOR | Default text editor|  
  |$0 | The name of the Bash script|
  |$1 | First argument to the Bash script|
  |$# | How many arguments were passed to the Bash script|
  |$@ | All the arguments supplied to the Bash script|
  |$? | The exit status of the most recently run process|
  |$$ | The process ID of the current script|
  |$USER | The username of the user running the script|
  |$HOSTNAME | The hostname of the machine the script is running on|
  |$SECONDS | The number of seconds since the script was started|
  |$RANDOM | Returns a different random number each time is it referred to|
  |$LINENO | Returns the current line number in the Bash script|

  ## Arithmetic in Bash
  We just enclose any mathematical expression inside double parentheses
  ```
  $(( expression ))
  ```
  
  |Expression |Description|
  | --- | --- |
  |a + b|addition (a plus b)|
  |a - b|subtracting (a minus b)|
  |a * b|multiplication (a times b)|
  |a / b|integer division (a divided by b)|
  |a % b|modulo (the integer remainder of a divided by b)|
  |a ** b|exponentiation (a to the power of b)|
  
  
 ## The Differences
  
| " "| ' ' |
| --- | --- |
| Interprets what's inside it | Interprets what's inside it literally|


## Bash If-else statement 

**Example:**
```
#!/bin/bash

echo -n "Enter a number: "
read VAR

if [[ $VAR -gt 10 ]]
then
  echo "The variable is greater than 10."
elif [[ $VAR -eq 10 ]]
then
  echo "The variable is equal to 10."
else
  echo "The variable is less than 10."
fi
```
## Conditions

#### Comparing Numerical Variables

| Expression in BASH | Evaluates to true when:
| :-----------: | :------------:
| `$a -eq $b` | a is equal to b
| `$a -ne $b` | a is not equal to b
| `$a -lt $b` | a is less than b
| `$a -gt $b` | a is greater than b
| `$a -ge $b` | a is greater than or equal to b
| `$a -le $b` | a is less than or equal to b

**Another way of comparing numerical values is to use ```((  ))``` instead of ```[[  ]]``` which allows you to use C-like operators.**
- Example:
`if [[ $a -eq $b ]]` becomes `if (( a == b ))`

#### Comparing String Variables
| Expression in BASH | Evaluates to true when:
| :-----------: | :------------:
| `$a = $b` or `$a == $b` | a is the same as b
| `$a != $b` | a is different from b
| `-z $a` | a is empty

#### Combining Conditions

| Expression in BASH | Evaluates to true when:
| :-----------: | :------------:
| `[[ cond. A \|\| cond. B ]]` | A OR B is true
| `[[ cond. A && cond. B ]]` | A AND B is true
| `[[ ! cond. A ]]` | A is false 

## Case statements

**Example:**
```
case $1 in
    start)
        echo starting
        ;;
    stop)
        echo stopping
        ;;
    restart)
        echo restarting
        ;;
    *)
        echo don\'t know
        ;;
esac
```

## For Loop

**Example:**
```
read x
for i in $(seq 1 $x)
do
    echo $i
done
````

## While Loops

**Break**
```
while [[ x -lt 10 ]]
do
    read i
    
    if [[ i -eq 0 ]]
    then 
        break
    fi
    echo $i
done

echo "break sent me here"
```
**Continue**
```
while [[ x -lt 10 ]]
do
    read i
    
    if [[ i -eq 0 ]]
    then 
        echo "Skipping the rest of the code!"
        continue
    fi
    echo $i
done
```

## Functions
```
function NAME #Function Definition
{
     #DoThings
}

NAME #Function call
```

**Passing arguments to a function**
```
function add
{
    echo $(($1 + $2))
}

add 3 5
```

## The Fork Bomb

```
:()        # Create a function named ‘ : ’
{          # Start of the function body
    : | :& # Calls itself, once in the foreground and once in the background
}          # End of the function body

:          # Function call
```
