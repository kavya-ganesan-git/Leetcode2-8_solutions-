# Leetcode2-8_solutions-
------> 1.spiral matrix
Given a positive integer n, generate an n x n matrix filled
with elements from 1 to n2 in spiral order.

-------> 2.Richest customer wealth
You are given an m x n integer grid accounts where
accounts[i][j] is the amount of money the ith customer
has in the jth bank. Return the wealth that the richest
customer has.
A customer's wealth is the amount of money they have in
all their bank accounts. The richest customer is the
customer that has the maximum wealth

code:
programming lan:java
class Solution {
    public int maximumWealth(int[][] accounts) {
        int sum=0,max=0;
        for(int i=0;i<accounts.length;i++)
        {
            for(int j=0;j<accounts[i].length;j++)
            {
                sum+=accounts[i][j];
            }
            if(sum>max)
            {
                max=sum;
            }
            sum=0;
        }
        return max;
    }
}

------> 3.Toeplitz matrix
Given an m x n matrix, return true if the matrix is Toeplitz.
Otherwise, return false.
A matrix is Toeplitz if every diagonal from top-left to
bottom-right has the same elements.

class Solution {
    public boolean isToeplitzMatrix(int[][] matrix) {
        for(int i=1;i<matrix.length;i++)
        {
            for(int j=1;j<matrix[i].length;j++)
            {
                if(matrix[i-1][j-1]!=matrix[i][j])
                {
                    return false;
                }
               
            }
       
        } 
        return true;
         }
    
}

------> 4.Matrix Diagonal Sum
Given a square matrix mat, return the sum of the matrix
diagonals.
Only include the sum of all the elements on the primary
diagonal and all the elements on the secondary diagonal
that are not part of the primary diagonal.

class Solution {
    public int diagonalSum(int[][] mat) {
        int sum=0;
        if(mat.length%2!=0)
        {
           for(int i=0;i<mat.length;i++)
           {
               if(i==mat.length/2)
               {
                   sum+=mat[i][i];
               }
               else{
                   sum+=mat[i][i]+mat[i][mat.length-i-1];
               }
           }
        }
        else{
        for(int i=0;i<mat.length;i++)
        {
            sum+=mat[i][i]+mat[i][mat.length-i-1];
        }
        }
        return sum;
    }
}

5.Count Negative Numbers in a Sorted Matrix

Given a m x n matrix grid which is sorted in non-increasing
order both row-wise and column-wise, return the number of
negative numbers in grid.

class Solution {
    public int countNegatives(int[][] grid) {
        int count=0;
        for(int i=0;i<grid.length;i++)
        {
            for(int j=0;j<grid[i].length;j++)
            {
                if(grid[i][j]<0)
                {
                    count++;
                }
            }
        }
        return count;
    }
}

6.Transpose Matrix

Given a 2D integer array matrix, return the transpose of
matrix.
The transpose of a matrix is the matrix flipped over its main
diagonal, switching the matrix's row and column indices.

class Solution {
    public int[][] transpose(int[][] matrix) {
        int ans[][]=new int[matrix[0].length][matrix.length];
        for(int i=0;i<matrix.length;i++)
        {
            for(int j=0;j<matrix[i].length;j++)
            {
                ans[j][i]=matrix[i][j];
            }
        }
        return ans;
 }
}

7.Set Matrix Zeroes

Given an m x n integer matrix matrix, if an element is 0,
set its entire row and column to 0's.




