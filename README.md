# irt_test
Package for calc difficult of test tasks and ability of test subjects by Rasch model (IRT 0).

## Installation
You can install irt_test using pip:

```bash
pip install irt-test
```

### Example Usage

For get logits of tasks and subjects use 'irt' function:

```python
import pandas as pd
from irt_test.irt import irt

# Get pandas DataFrame with test results
df = pd.read_excel('test.xlsx', index_col=0)

# Get logits and additional info from IRT0 model
irt_result = irt(df)

# Abilites of test subjects
irt_result.abilities

# Difficult of test tasks
irt_result.difficult

# "IRT model error
irt_result.err

# Can't get logits for these subjects
irt_result.rejected_subjects

# Can't get logits for these tasks
irt_result.rejected_tasks
```
# irt_result.abilities (pd.Series)
Julia      4.720945
Ivan       3.290194
Anna       1.978364
Peter      1.978364
Helen      1.978364
Bill       0.711974
Tony      -0.451242
Dmitry    -2.236696
Natasha   -3.034704
dtype: float64

# irt_result.difficult (pd.Series)
Task 1    -2.847789
Task 2    -2.847789
Task 3    -2.847789
Task 4    -2.847789
Task 5    -1.404599
Task 6    -0.212051
Task 7     2.396402
Task 8     1.593047
Task 9     4.509178
Task 10    4.509178
dtype: float64

# irt_result.err (float)
0.0196

# irt_result.rejected_subjects (list[str])
['Jimmy']

# irt_result.rejected_tasks (list[str])
 ['Task 11']


