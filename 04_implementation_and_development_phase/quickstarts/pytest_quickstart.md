# Pytest Quickstart:
## To install pytest, run:
```bash
pip install pytest
```

## An example function:
```python
# fetch_data.py

# Your function that fetches data from an external API
def fetch_data(api_url):
    # some code that fetches data
    pass

```

## A simple test case using pytest could look like this:
```python
# test_fetch_data.py
from unittest.mock import patch
import pytest

from fetch_data import fetch_data

# Fixtures
@pytest.fixture
def mock_data():
    return {'key': 'value'}

# Your test case
def test_fetch_data_given_mocked_api_expect_correct_data_returned(mock_data):
    # Mocks & Arrange
    with patch('your_module_name.fetch_data') as mock_fetch:
        mock_fetch.return_value = mock_data

        # Act
        result = fetch_data('some_api_url')

        # Assert
        assert result == mock_data


```
- In this example, the test function is now named `test_fetch_data_given_mocked_api_expect_correct_data_returned`, which clearly describes what the test is doing:
    - Testing the `fetch_data` function
    - Given a mocked API
    - Expects to get the correct data returned
    - This makes it easier to understand the purpose of the test, especially when you have a large number of tests.

## To run the test, execute:
```bash
pytest test_fetch_data.py
```

## External `pytest` Examples
- [Real Python's Guide on Python Testing with Pytest](https://realpython.com/python-testing/)