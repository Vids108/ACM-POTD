Pascal's Triangle
This method builds Pascal’s Triangle row by row using iteration. Each row starts and ends with 1, so we 
initialize rows with all 1s. For inner elements, we use the property that each value equals the sum of the 
two values directly above it in the previous row. Specifically, row[j] = prev_row[j-1] + prev_row[j]. We store
previously computed rows in a list and reuse them to calculate the next row efficiently. This avoids recomputation
and ensures an optimal time complexity of O(n²), where n is the number of rows. The approach is simple, intuitive,
and commonly used in dynamic programming problems.

CODE:
class Solution:
    def generate(self, numRows: int):
        triangle = []

        for i in range(numRows):
            row = [1] * (i + 1)
            for j in range(1, i):
                row[j] = triangle[i - 1][j - 1] + triangle[i - 1][j]
            triangle.append(row)

        return triangle
