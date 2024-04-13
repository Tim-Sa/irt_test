# irt_test
Package for calc difficult of test tasks and ability of test subjects by Rasch model (IRT 0).

## Installation
You can install irt_test using pip:

```bash
pip install irt-test

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

# "IRT model error:"
irt_result.err

# Can't get logits for these subjects
irt_result.rejected_subjects

# Can't get logits for these tasks
irt_result.rejected_tasks
