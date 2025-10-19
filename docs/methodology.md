# Experiment Methodology

## Research Question
Does numeric representation (digits vs. spelled-out words vs. quoted strings) affect the correctness of LLM responses for numerical and data-science tasks?

## Hypothesis
I hypothesize that numeric digit representation will yield higher accuracy than spelled-out words or quoted string representations due to reduced ambiguity in parsing.

## Experimental Design

### Design Type
Within-subjects, paired comparison design

### Independent Variable
Numeric representation format (3 levels):
- **Numeric (N)**: Standard digits (e.g., `12`, `3.5`)
- **Words (W)**: Spelled-out numbers (e.g., `twelve`, `three point five`)
- **Strings (S)**: Quoted string digits (e.g., `"12"`, `"3.5"`)

### Dependent Variables
1. **Correctness**: Binary (correct/incorrect) based on expected answer
2. **Step-by-step reasoning**: Presence of calculation steps (Y/N)
3. **Output format compliance**: Final answer on single line, numeric only (Y/N)

### Tasks
10 numerical tasks across 6 categories:
1. Arithmetic (simple sum, percentage change, sum of sequence)
2. Statistics (mean, weighted average, standard deviation)
3. Conversion (unit conversion)
4. Probability (basic probability)
5. Algebra (slope calculation)
6. Linear algebra (matrix multiplication)

### Procedure
1. Each task presented in all 3 formats (30 total prompts)
2. Format order randomized per task to control for order effects
3. Standardized instruction prefix for all prompts
4. Single LLM session to maintain consistency

### LLM Configuration
- **Model**: Claude Sonnet 4.5 (claude-sonnet-4-5-20250929)
- **Date**: October 18, 2025
- **Temperature**: Default 
- **Context**: New conversation, no prior context

### Control Measures
- Identical instruction format across all prompts
- Same task computational difficulty across formats
- Randomized presentation order
- Single-session execution (eliminates session variability)

## Scoring Rubric

For each response, I score:

| Criterion | Values | Description |
|-----------|--------|-------------|
| Correctness | Y/N | Does final answer match expected value? |
| Steps shown | Y/N | Are intermediate calculations displayed? |
| Format compliance | Y/N | Is final answer on single line, numeric only? |
| Error type | categorical | If incorrect: parsing, calculation, format, refusal |

### Correctness Tolerance
- Integers: exact match required
- Decimals: ±0.01 tolerance or 4 significant figures
- Matrices: element-wise exact match

## Expected Outcomes

### Primary Prediction
Accuracy ranking: Numeric > Words > Strings

### Secondary Predictions
1. String format may trigger concatenation errors
2. Word format may cause parsing difficulties with decimals
3. Step-by-step reasoning quality may vary by format

## Limitations
- Small sample size (pilot study)
- Single LLM model tested
- Manual scoring (potential bias)
- No statistical power analysis
- Limited task diversity

## Future Directions
- Larger task set (100+ prompts)
- Multiple LLM models
- Automated scoring pipeline
- Statistical significance testing
- Cross-model generalization studies
