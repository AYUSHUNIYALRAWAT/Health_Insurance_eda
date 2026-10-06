# Data Dictionary

## Original Dataset

| Column | Type | Description |
|---|---|---|
| `age` | Integer | Age of the beneficiary |
| `sex` | Categorical | Sex of the beneficiary |
| `bmi` | Float | Body Mass Index |
| `children` | Integer | Number of children/dependents |
| `smoker` | Categorical | Smoking status |
| `region` | Categorical | Residential region |
| `charges` | Float | Medical/insurance charges |

## Engineered Columns

| Column | Description |
|---|---|
| `is_female` | Encoded sex indicator: female = 1, male = 0 |
| `is_smoker` | Encoded smoking indicator as implemented in the notebook: yes = 0, no = 1 |
| `region_northwest` | One-hot encoded region indicator |
| `region_southeast` | One-hot encoded region indicator |
| `region_southwest` | One-hot encoded region indicator |
| `bmi_category` | BMI group created before one-hot encoding |
| `bmi_category_normal` | One-hot encoded BMI category |
| `bmi_category_overweight` | One-hot encoded BMI category |
| `bmi_category_obese` | One-hot encoded BMI category |

### Important implementation note

The notebook maps `smoker` as:

```python
{'yes': 0, 'no': 1}
```

Therefore, `is_smoker = 0` means smoker and `is_smoker = 1` means non-smoker. The name is retained exactly as implemented in the notebook.
