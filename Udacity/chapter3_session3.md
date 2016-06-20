# Chapter 3: Problem Set

=================================

## 1. Difference between + and append


	    # Investigating adding and appending to lists
		# If you run the following four lines of codes, what are list1 and list2?
		
		list1 = [1,2,3,4]
		list2 = [1,2,3,4]
		
		list1 = list1 + [5, 6]
		list2.append([5, 6])
		
		# to check, you can print them out using the print statements below.
		
		print "showing list1 and list2:"
		print list1
		print list2
	

	The answer will be:
	
		showing list1 and list2:
		[1, 2, 3, 4, 5, 6]
		[1, 2, 3, 4, [5, 6]]


## 2. Symmetric Square

		# A list is symmetric if the first row is the same as the first column,
		# the second row is the same as the second column and so on. Write a
		# procedure, symmetric, which takes a list as input, and returns the
		# boolean True if the list is symmetric and False if it is not.

		def symmetric(square):
		    if square == []:
		        return True
		    squareSize = len(square)     # Extract size of grid  (defined by number of rows)
		    squareCols = len(square[0])  # Extract number of columns
		    if not (squareSize == squareCols):  # If grid is non-square
		        return False
		    i = 0
		    while i <= (squareSize - 1):
		        j = 0
		        while j <= (squareSize - 1):   # for each entry in ith row/column
		            # work through the i*th row
		            if not (square[i][j] == square[j][i]):
		                return False
		            j = j + 1
		        i = i + 1   # next row/column
		    return True  # Nothing was wrong.
		
		    
		print symmetric([[1, 2, 3],
		                [2, 3, 4],
		                [3, 4, 1]])
		# >>> True
		
		print symmetric([["cat", "dog", "fish"],
		                ["dog", "dog", "fish"],
		                ["fish", "fish", "cat"]])
		# >>> True
		
		print symmetric([["cat", "dog", "fish"],
		                ["dog", "dog", "dog"],
		                ["fish","fish","cat"]])
		# >>> False
		
		print symmetric([[1, 2],
		                [2, 1]])
		# >>> True
		
		print symmetric([[1, 2, 3, 4],
		                [2, 3, 4, 5],
		                [3, 4, 5, 6]])
		# >>> False
		
		print symmetric([[1,2,3],
		                [2,3,1]])
		# >>> False

## 3. Mean of a List

		# The mean of a set of numbers is the sum of the numbers divided by the
		# number of numbers. Write a procedure, mean, which takes a list of numbers
		# as its input and return the mean of the numbers in the list.
		
		# Hint: You will need to work out how to make your division into decimal
		# division instead of integer division. You get decimal division if any of
		# the numbers involved are decimals.
		
		def list_mean(listOfNumbers):
		    if listOfNumbers == []:
		        return 0.0
		    total = 0.0
		    for e in listOfNumbers:
		        total += e
		    result = total / len(listOfNumbers)
		    return result
		
		print list_mean([1,2,3,4])
		#>>> 2.5
		print list_mean([1,3,4,5,2])
		#>>> 3.0
		print list_mean([])
		
		print list_mean([2])
		#>>> 2.0

