# assert
```python
from calculator import square


def main():
    test_square()


def test_square():
    try:
        assert square(2) == 4
    except AssertionError:
        print("2 squared is not 4")
    try:
        assert square(3) == 9
    except AssertionError:
        print("3 squared is not 9")
    try:
        assert square(-2) == 4
    except AssertionError:
        print("-2 squared is not 4")
    try:
        assert square(-3) == 9
    except AssertionError:
        print("-3 squared is not 9")
    try:
        assert square(0) == 0
    except AssertionError:
        print("0 squared is not 0")


if __name__ == "__main__":
    main()


# pytest
```python
  import pytest

  from calculator import square


  def test_positive():
      assert square(2) == 4
      assert square(3) == 9


  def test_negative():
      assert square(-2) == 4
      assert square(-3) == 9


  def test_zero():
      assert square(0) == 0


  def test_str():
      with pytest.raises(TypeError):
          square("cat")

## organizing tests into folder
- objective: run multiple tests with a single command
- steps:
    - in the terminal window, execute `mkdir test` to create a folder called `test`
    - type in the terminal window `code test/test_hello.py` to create a test within that folder
    - modify the file
    - typing c`ode test/__init__.py` to create the __init__ file. (pytest will not allow us to run tests as a folder without a special __init__ file, but Even leaving this __init__.py file empty, pytest is informed that the whole folder containing __init__.py has tests that can be run.)
    - typing `pytest test` in the terminal, you can run the entire test folder of code.

# reference
https://cs50.harvard.edu/python/2022/notes/5/
