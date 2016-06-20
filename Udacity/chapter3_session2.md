#Chap 3: Session 2 - Problem Set


### Quiz: Lists

Fill in the initial values of elements of `p` to produce the behavior show below:

p =[?,?,?]

	p[0] = p[0] + p[1]
	p[1] = p[0] + p[2]
	p[2] = p[0] + p[1]
	print p => [1,2,3]
	
>p = [1,0,1]


### Quiz: Mutating Lists

Which of the following procedures leaves the value passed in as the input unchanged?

	1. def proc1(p):
			p[0] = p[1]
			
	2. def proc2(p):
			p = p +[1]
			
	3. def proc3(p):
			q = p
			p.append(3)
			q.pop()
			
	4. def proc4(p):
			q = []
			while p:
				q.append(p.pop())
			while q:
				p.append(q.pop())
				
> Result : 2,3 vs 4

### Quiz: Product Lists:

Define a procedure, product_list, that takes as input a list of numbers, and returns a number that is the result of multiplying all those numbers together.

		def product_list(list_of_numbers):
		    result = 1
		    for e in list_of_numbers:
		        result = result * e
		    return result
		    
		    
		print product_list([9])
		#>>> 9
		
		print product_list([1,2,3,4])
		#>>> 24
		
		print product_list([])
		#>>> 1

### Quiz: Greatest

Define a procedure, greatest, that takes as input a list of positive numbers, and returns the greatest number in that list. If the input list is empty, the output should be 0.

		def greatest(list_of_numbers):
		    max = 0
		    for e in list_of_numbers:
		        if e > max:
		            max = e
		    return max
		
		
		
		print greatest([4,23,1])
		#>>> 23
		print greatest([])
		#>>> 0