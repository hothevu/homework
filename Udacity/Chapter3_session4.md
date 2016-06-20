# Chap 3.4 Problem Set
==========================================

## 1.Recognize Identity Matrix

		# Challenge Posted by Ashwath from forums
		# Given a list of lists representing a n * n matrix as input, 
		# define a  procedure that returns True if the input is an identity matrix 
		# and False otherwise.
		
		# An IDENTITY matrix is a square matrix in which all the elements 
		# on the principal/main diagonal are 1 and all the elements outside 
		# the principal diagonal are 0. 
		# (A square matrix is a matrix in which the number of rows 
		# is equal to the number of columns)
		
		def is_identity_matrix(square):
		    if square == []:
		        return True
		    squareSize = len(square)     # Extract size of grid  (defined by number of rows)
		    numCols = len(square[0])  # Extract number of columns
		    if not (squareSize == numCols):  # If grid is non-square
		        return False
		    i = 0
		    while i <= (squareSize - 1):
		        j = 0
		        while j <= (squareSize - 1):   # for each entry in ith row/column
		            # work through the ith row/column               
		            if not (square[i][j] == square[j][i]):                
		                return False
		            if (i == j):
		                if not (square[i][j] == 1):
		                    return False
		            else:
		                if not(square[i][j] == 0):
		                    return False
		            j = j + 1
		        i = i + 1   # next row/column
		    return True  # Nothing was wrong.
		
		
		# Test Cases:
		
		matrix1 = [[1,0,0,0],
		           [0,1,0,0],
		           [0,0,1,0],
		           [0,0,0,1]]
		print is_identity_matrix(matrix1)
		#>>>True
		
		matrix2 = [[1,0,0],
		           [0,1,0],
		           [0,0,0]]
		
		print is_identity_matrix(matrix2)
		#>>>False
		
		matrix3 = [[2,0,0],
		           [0,2,0],
		           [0,0,2]]
		
		print is_identity_matrix(matrix3)
		#>>>False
		
		matrix4 = [[1,0,0,0],
		           [0,1,1,0],
		           [0,0,0,1]]
		
		print is_identity_matrix(matrix4)
		#>>>False
		
		matrix5 = [[1,0,0,0,0,0,0,0,0]]
		
		print is_identity_matrix(matrix5)
		#>>>False
		
		matrix6 = [[1,0,0,0],  
		           [0,1,0,2],  
		           [0,0,1,0],  
		           [0,0,0,1]]
		
		print is_identity_matrix(matrix6)
		#>>>False
		
		matrix7 = [[1, -1, 1],
		           [0, 1, 0],
		           [0, 0, 1]]
		print is_identity_matrix(matrix7)
		#>>>False           

## 2. Numbers in Lists

		# Numbers in lists by SeanMc from forums
		# define a procedure that takes in a string of numbers from 1-9 and
		# outputs a list with the following parameters:
		# Every number in the string should be inserted into the list.
		# If a number x in the string is less than or equal 
		# to the preceding number y, the number x should be inserted 
		# into a sublist. Continue adding the following numbers to the 
		# sublist until reaching a number z that
		# is greater than the number y. 
		# Then add this number z to the normal list and continue.
		
		#Hint - "int()" turns a string's element into a number
		
		# Credit goes to paidhima of Udacity forum
		def numbers_in_lists(string):
		    mainList = [int(string[0])]
		    subList = []
		    max = int(string[0])
		    for e in string[1:]:
		        num = int(e)
		        if num > max:
		            if subList:
		                mainList.append(subList)
		                subList = []
		            mainList.append(num)
		            max = num
		        else:
		            subList.append(num)
		    if subList:
		        mainList.append(subList)
		    return mainList 
		
		#testcases
		string = '543987'
		result = [5,[4,3],9,[8,7]]
		print repr(string), numbers_in_lists(string) == result
		string= '987654321'
		result = [9,[8,7,6,5,4,3,2,1]]
		print repr(string), numbers_in_lists(string) == result
		string = '455532123266'
		result = [4, 5, [5, 5, 3, 2, 1, 2, 3, 2], 6, [6]]
		print repr(string), numbers_in_lists(string) == result
		string = '123456789'
		result = [1, 2, 3, 4, 5, 6, 7, 8, 9]
		print repr(string), numbers_in_lists(string) == result




## 3 . Frequency Analysis


		# Crypto Analysis: Frequency Analysis
		#
		# To analyze encrypted messages, to find out information about the possible 
		# algorithm or even language of the clear text message, one could perform 
		# frequency analysis. This process could be described as simply counting 
		# the number of times a certain symbol occurs in the given text. 
		# For example:
		# For the text "test" the frequency of 'e' is 1, 's' is 1 and 't' is 2.
		#
		# The input to the function will be an encrypted body of text that only contains 
		# the lowercase letters a-z. 
		# As output you should return a list of the normalized frequency 
		# for each of the letters a-z. 
		# The normalized frequency is simply the number of occurrences, i, 
		# divided by the total number of characters in the message, n.
		
		def freq_analysis(content):
		    text = 'abcdefghijklmnopqrstuvwxyz'
		    freq_list = [0.0] *26
		    for i in content:
		        freq_list[text.find(i)] +=  1.0 / len (content)
		    return freq_list
		
		
		
		#Tests
		
		print freq_analysis("abcd")
		#>>> [0.25, 0.25, 0.25, 0.25, 0.0, ..., 0.0]
		
		print freq_analysis("adca")
		#>>> [0.5, 0.0, 0.25, 0.25, 0.0, ..., 0.0]
		
		print freq_analysis('bewarethebunnies')
		#>>> [0.0625, 0.125, 0.0, 0.0, ..., 0.0]
		
		
