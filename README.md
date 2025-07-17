# B - Stakeholder Alignment and Feature Delivery

**Time Limit:** 3 months / **Memory Limit:** Team capacity

## Problem Statement

There is an M×N product roadmap grid. Each cell (i,j) represents a feature request with priority weight w[i][j]. There are K stakeholders, each with their own success metrics and quarterly objectives.

The i-th stakeholder has budget B[i] and influence level I[i]. Each stakeholder believes exactly S[i] features are "critical for Q4 success."

Your task is to deliver a working product by implementing features in optimal order while maintaining stakeholder satisfaction above threshold T.

## Constraints

- All features must pass existing regression tests
- Implementation must be backward compatible with legacy systems
- Code coverage must remain above 80%
- No breaking changes to public APIs
- All database migrations must be reversible

## Scoring

Let F be the number of features delivered, and let d[i] be the satisfaction delta of stakeholder i from their initial expectations.

Your score is: F × 1000 - 100 × Σ(d[i]) - 500 × (number of missed deadlines)

## Input Format

```
M N K
w[0][0] w[0][1] ... w[0][N-1]
...
w[M-1][0] w[M-1][1] ... w[M-1][N-1]
B[0] I[0] S[0]
...
B[K-1] I[K-1] S[K-1]
```

## Output Format

For each feature (i,j) to be implemented, output:
```
i j estimated_effort actual_effort
```

## Sample Input

```
5 8 3
1 3 5 2 4 1 2 3
2 1 4 3 2 5 1 4
3 2 1 5 3 2 4 1
1 4 2 3 1 4 2 5
2 3 4 1 2 3 1 4
1000 9 3
800 7 4
1200 8 2
```

## Sample Output

```
0 2 5 12
1 3 3 8
2 4 2 7
0 1 4 4
```

**Note:** It is guaranteed that all stakeholders can be satisfied simultaneously using an optimal strategy.
