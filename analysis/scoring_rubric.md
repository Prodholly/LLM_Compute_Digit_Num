# Scoring Rubric

## Quick Reference Answers

| Task | Expected Answer | Tolerance |
|------|----------------|-----------|
| 1. Simple sum | 54.5 | exact |
| 2. Mean | 13.2 | ±0.01 |
| 3. Weighted avg | 17.5 | exact |
| 4. Percentage change | 33.3333 (or 33.33%) | ±0.01 |
| 5. Unit conversion | 5500 | exact |
| 6. Probability | 0.027778 (1/36) | ±0.0001 |
| 7. Slope | 3 | exact |
| 8. Std deviation | 2.0 | ±0.01 |
| 9. Matrix mult | [[4,4],[10,8]] | exact |
| 10. Sum sequence | 120 | exact |

## Detailed Calculations

### Task 1: Simple Sum
```
12 + 37 + 5.5 = 54.5
```

### Task 2: Mean
```
Numbers: 4, 8, 15, 16, 23
Sum: 66
Count: 5
Mean: 66/5 = 13.2
```

### Task 3: Weighted Average
```
Values: 10, 20
Weights: 1, 3
Weighted sum: (10×1) + (20×3) = 10 + 60 = 70
Sum of weights: 1 + 3 = 4
Weighted average: 70/4 = 17.5
```

### Task 4: Percentage Change
```
From: 45
To: 60
Change: 60 - 45 = 15
Percent: (15/45) × 100 = 33.3333%
```

### Task 5: Unit Conversion
```
5.5 km × 1000 m/km = 5500 m
```

### Task 6: Probability
```
P(6 on first roll) = 1/6
P(6 on second roll) = 1/6
P(both) = (1/6) × (1/6) = 1/36 ≈ 0.027778
```

### Task 7: Slope
```
Points: (2, 5) and (6, 17)
Slope = (y₂ - y₁)/(x₂ - x₁) = (17 - 5)/(6 - 2) = 12/4 = 3
```

### Task 8: Population Standard Deviation
```
Data: 2, 4, 4, 4, 5, 5, 7, 9
Mean: (2+4+4+4+5+5+7+9)/8 = 40/8 = 5
Squared deviations: (2-5)²=9, (4-5)²=1, (4-5)²=1, (4-5)²=1, 
                    (5-5)²=0, (5-5)²=0, (7-5)²=4, (9-5)²=16
Sum of squared deviations: 9+1+1+1+0+0+4+16 = 32
Variance: 32/8 = 4
Std dev: √4 = 2.0
```

### Task 9: Matrix Multiplication
```
A = [[1,2],[3,4]]
B = [[2,0],[1,2]]
A×B = [[1×2+2×1, 1×0+2×2], [3×2+4×1, 3×0+4×2]]
    = [[4, 4], [10, 8]]
```

### Task 10: Sum of Sequence
```
Sum of 1 to 15 = n(n+1)/2 = 15×16/2 = 120
```

## Error Classification

### Error Types
1. **Parsing error**: LLM failed to interpret numbers correctly
2. **Calculation error**: Wrong computation despite correct parsing
3. **Format error**: Correct answer but wrong output format
4. **Refusal**: LLM refused to compute (common with quoted strings)
5. **Concatenation**: Treated strings as text, not numbers (e.g., "12" + "37" = "1237")

## Scoring Template

Here is the template used for scoring each response:
```
Prompt ID: _______
Correct: Y / N
Steps shown: Y / N
Format compliant: Y / N
LLM answer: _______
Expected answer: _______
Error type (if incorrect): _______
Notes: _______
```
