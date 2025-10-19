# Experiment Results Summary

**Date**: October 18, 2025  
**Model**: Claude Sonnet 4.5 (claude-sonnet-4-5-20250929)  
**Total Prompts**: 30 (10 tasks × 3 formats)

## Key Finding

**All 30 responses were correct (100% accuracy across all formats).**

This is a surprising and significant result that differs from the initial hypothesis that numeric format would outperform words and strings.

## Results by Format

| Format | N | Correct | Accuracy | Steps Shown | Format Compliant |
|--------|---|---------|----------|-------------|------------------|
| Numeric | 10 | 10 | 100% | 10/10 | 10/10 |
| Words | 10 | 10 | 100% | 10/10 | 10/10 |
| Strings | 10 | 10 | 100% | 10/10 | 10/10 |
| **Total** | **30** | **30** | **100%** | **30/30** | **30/30** |

## Observations

### 1. Explicit Conversion Strategy
Claude Sonnet 4.5 systematically handles non-numeric formats by:
- **Words format**: Adds explicit "Convert words to numbers" step
- **Strings format**: Adds explicit "Convert strings to numbers" step
- **Numeric format**: Proceeds directly to computation

### 2. Consistent Step-by-Step Reasoning
All 30 responses showed:
- ✅ Clear intermediate calculations
- ✅ Final answer on single line
- ✅ Numeric-only final output

### 3. No Format-Specific Errors
Contrary to expectations:
- ❌ No string concatenation errors (e.g., "12" + "37" = "1237")
- ❌ No parsing failures for decimal words (e.g., "five point five")
- ❌ No calculation mistakes in any format

## Results by Task Type

| Task Type | N | Correct | Accuracy |
|-----------|---|---------|----------|
| Arithmetic | 9 | 9 | 100% |
| Statistics | 9 | 9 | 100% |
| Algebra | 3 | 3 | 100% |
| Linear Algebra | 3 | 3 | 100% |
| Conversion | 3 | 3 | 100% |
| Probability | 3 | 3 | 100% |

## Implications

### For Prompt Engineering
1. **Format flexibility**: Claude Sonnet 4.5 handles all three numeric representation formats equally well
2. **Explicit instructions work**: The "step-by-step" instruction prompt consistently produces correct reasoning
3. **Robustness**: No format-specific vulnerabilities detected in this pilot

### For Future Research
1. **Scale up**: Test with 100+ tasks to detect subtle differences
2. **Model comparison**: Test older/smaller models that may show format sensitivity
3. **Edge cases**: Include more complex decimals, negative numbers, scientific notation
4. **Adversarial**: Test intentionally ambiguous formats (e.g., "1,000" vs "1.000")

## Limitations
- Small sample (n=30)
- Single model tested
- Simple tasks (all solvable in <10 steps)
- No statistical significance testing
