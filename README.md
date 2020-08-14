n = int(input())
matrix = [[0] * n for i in range (n)]
number, factor = 1, 0
matrix[n // 2][n // 2] = n ** 2
for series in range(n // 2):
    for i in range(n - factor):
        matrix[series][i + series] = number
        number += 1
    for i in range(series + 1, n - series):
        matrix[i][-series - 1] = number
        number += 1
    for i in range(series + 1, n - series):
        matrix[-series - 1][-i - 1] = number
        number += 1
    for i in range(series + 1, n - (series + 1)):
        matrix[-i - 1][series] = number
        number += 1
    factor += 2
for i in matrix:   #тут выводиться матрица 
    print(*i)
