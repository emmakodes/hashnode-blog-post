# Testing in Software Development

# Software Testing

Software Testing is a process of evaluating software applications to ensure they work efficiently in terms of performance, correctness, and completeness.

# Importance of Software Testing

It helps to:

*   Identify bugs
    
*   Identify gaps in a product or software
    
*   detect poor design etc
    

# How to Implement Unit Test for your Software

There are various levels of testing in software development. They include unit testing, integration testing, system testing, and acceptance testing.

In unit testing, you test specific individual components. These components can be viewed as a method, function, or object.

We are going to implement unit testing in python.

Let's say we have a python file "addition.py" with the following code to sum numbers:

```python
def add(firstnumber, secondnumber):
    return firstnumber + secondnumber
```

To test the above code to ensure it can calculate the sum of numbers,

*   We will first install pytest. Pytest is a Python testing framework that helps to write various types of software tests. Run the following command on your terminal.
    

```bash
pip install -U pytest
```

*   create a python file test\_addition.py where we are going to write our test cases to test the above code. Add the following code:
    

```python
from addition import add
import pytest

def test_add():
    assert add(5, 6) == 11
```

Above, we import the add function and also pytest, then we defined the test\_add() function. In the test\_add() function, we called the add() function and passed 5 and 6 as arguments. Pytest will sum the value of 5 and 6, if the sum is 11 then your test passed else your test failed.

**Note: The name of your test function has to start with test.**

*   Run pytest on the terminal with the following command and specify the file over which you are doing your test, in our case "test\_addition.py":
    

```plaintext
python -m pytest test_addition.py
```

You will see the following output on the terminal:

\============== test session starts ========================

platform win32 -- Python 3.8.7rc1, pytest-7.2.0, pluggy-1.0.0 rootdir: C:\\Users\\HP 15\\PycharmProjects\\code\\onetwo collected 1 item

test\_addition.py . \[100%\]

\=============== 1 passed in 0.15s ========================

Notice the full stop after the test\_addition.py line and also the statement "1 passed" since we have one test case or function defined. Our test passed, you can say your add function can add two integers correctly.

Thanks for reading!!