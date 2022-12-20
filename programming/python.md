# Python

## Operators

| Arithmetic | Name           |     | Comparision | Name                     |     | Logical | Description                                  |
| ---------- | -------------- | --- |:-----------:|:------------------------ | --- | ------- | -------------------------------------------- |
| +          | Addition       |     |     ==      | Equal                    |     | *and*   | Returns *True* if both statements are true   |
| -          | Subtraction    |     |     !=      | Not equal                |     | *or*    | Returns *True* if either statements are true |
| *          | Multiplication |     |      >      | Greater than             |     | *not*   | Reverse the result, *False* if *True*                                             |
| /          | Divison        |     |      <      | Less than                |     |         |                                              |
| %          | Modulus        |     |     >=      | Greater than or equal to |     |         |                                              |
| **         | Exponentiation |     |     <=      | Less than or equal to    |     |         |                                              |
| //         | Floor division |     |             |                          |     |         |                                              |

## Functions

### if / elif / else Function

```python
if <conditional>:
	<Statement to be executed if the conditional evaluates to be True>
```

* Conditional can be any condition based on a combonation of one or more variables
* If this conditional evaluates to be true then the statement is executed and everything else below is skipped
* The colon (:) following the conditional is required

```python
if <conditional>:
	<Statement to be executed if the conditional evaluates to be True>
elif <conditional>:
	<Statement to be executed if the conditional evaluates to be True>
```
