# irt_test
Package for calc difficult of test tasks and ability of test subjects by Rasch model (IRT 0).

## Installation
You can install irt_test using pip:

```bash
pip install irt-test
```

### Example Usage
Input DataFrame example:
|       |   Task 1 |   Task 2 |   Task 3 |   Task 4 |   Task 5 |
|:------|---------:|---------:|---------:|---------:|---------:|
| Julia |        1 |        0 |        1 |        1 |        1 |
| Ivan  |        1 |        1 |        1 |        0 |        1 |
| Anna  |        1 |        0 |        0 |        0 |        1 |
| Peter |        0 |        0 |        0 |        1 |        1 |

For get logits of tasks and subjects use 'irt' function:

```python
from irt_test.irt import irt

# Get logits and additional info from IRT0 model
irt_result = irt(df)
```

```python
# Abilites of test subjects
irt_result.abilities
```
|       |        0 |
|:------|---------:|
| Julia |  1.32193 |
| Ivan  |  1.32193 |
| Anna  | -1.32193 |
| Peter | -1.32193 |

```python
# Difficult of test tasks
irt_result.difficult
```
|        |            0 |
|:-------|-------------:|
| Task 1 | -1.48486     |
| Task 2 |  1.48486     |
| Task 3 | -8.53067e-17 |
| Task 4 | -8.53067e-17 |

```python
# "IRT model error
irt_result.err
```
0.0196
```python
# Can't get logits for these subjects
irt_result.rejected_subjects
```
[]
```python
# Can't get logits for these tasks
irt_result.rejected_tasks
```
['Task 5']


