
# timeit Quickstart:
## You can use `timeit` in your Python script as follows:
```python
import timeit

def example_function():
    return sum(range(100))

# Measure the execution time of 'example_function'
execution_time = timeit.timeit("example_function()", globals=globals(), number=1000)
print(f"Execution time: {execution_time} seconds")
```

## Alternatively, you can use it from the command line:
```bash
python -m timeit -s 'from your_script import example_function' 'example_function()'
```
- This will output the average time taken for executing `example_function()`.