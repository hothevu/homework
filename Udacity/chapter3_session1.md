#Chapter 3 Udacity : Data


 **Chapter 3 : we learn about the list and practice with lists**


* Different between strings and lists: 

let's example string s and list p:

    s= 'yabba!' => surrounded by single or double quotes

	p = ['y', 'a', 'b', 'a', '!' ] => surrounded by brackets

	s[0] -> 'y'

	p[0] -> 'y'

	s[2:4] -> 'bb'

	p[2:4] -> ['b','b']
	
	

**Quiz: Stooges**

* Define a variable, stooges, whose value is a list of the names of the Three Stooges: "Moe", "Larry", and "Curly."

	```
	Stooges = ['Moe', 'Larry', 'Curly']
	```

* define a procedure, how_many_days, that takes as input a number representing a month, and outputs the number of days in that month.

>     def how_many_days(month_number):
>     	return days_in_month[month_number-1]

* countries = [['China','Beijing',1350],
             ['India','Delhi',1210],
             ['Romania','Bucharest',21],
             ['United States','Washington',307]]

Write code to print out the capital of India by accessing the list

    print countries[1][1]

* countries = [['China','Beijing',1350],
             ['India','Delhi',1210],
             ['Romania','Bucharest',21],
             ['United States','Washington',307]]

What multiple of Romania's population is the population of China? Calculate this by accessing the list and dividing the population of China (1350) by the population of Romania (21). Please print your result.

    print countries[0][2]/countries[2][2]

* stooges = ['Moe','Larry','Curly']

but in some Stooges films, Curly was replaced by Shemp. Write one line of code that changes the value of stooges to be:
	 `stooges[2] ='Shemp'`

* What is the value of agent[2] after the following code runs

    spy = [0,0,7]

    agent = spy

    spy[2] = agent[2] + 1

> 8

* Define a procedure, replace_spy,that takes as its input a list of three numbers, and modifies the value of the third element in the input list to be one more than its previous value.

	spy = [0,0,7]
	
	
	def replace_spy(spy):
	
	spy[2] += 1
	
	return spy


* Quiz: Len quiz: What is the value of len(p) after running the following code:

    p = [1, 2]

	p.append(3)

	p = p + [4, 5]

	len(p) → ?

>5

* Quiz: Append Quiz: What is the value of len(p) after running:

    p = [1, 2]

	q = [3, 4]

	p.append(q)

	len(p) → ?

>3

* Quiz : Loops on Lists


		def print_all_elements(p):
		    i = 0
		    while __________:
		          print p[i]
		          i = i + 1

>i < len(p)

* For loops:

		def print_all_elements(p):
		    for e in p:
		        print e

* Quiz: Sum List

Example: sum_list([2, 7, 4]) → 13

		def sum_list(n):
		    result = 0
		    for e in n:
		        result = result + e
		    return result

* Quiz: Measure Udacity

Define a procedure, measure_udacity, that takes as its input a list of strings, and outputs a number that is a count of the number of elements in the input list that start with an uppercase letter 'U'.

For example: 

		measure_udacity(['Dave', 'Sebastian', 'Katy'])
		0
		
		measure_udacity(['Umika', 'Umberto'])
		2
Code:

		def measure_udacity(a):
		    count = 0
		    for e in a:
		        if e[0] == 'U':
		            count += 1
		    return count

* Quiz: Find Element

Define a procedure, find_element, that takes as its input a list and a value of any type, and outputs the index of the first element in the input list that matches the value. If there is no matching element, output -1.

Examples: 

		find_element([1, 2, 3], 3) → 2
		find_element(['alpha', 'beta'], 'gamma') → -1

code: 

		def find_element(a,a):
		    result = -1
		    for e in a:
		        if k == e:
		            result = e -1
		    return result

* Index 

There are many other ways to define find_element. A built-in list operation that we have not yet introduced that makes it easier to write find_element is the index method:

		<''list''>.index(<''value''>) → <''position''> or error

Examples:

		p = [0, 1, 2]
		print p.index(2)
		2
		
		p = [0, 1, 2, 2, 2]
		print p.index(2)
		2

The output is True if the list contains an element matching value, and False if it does not.

* Quiz: Index:

Define a procedure, find_element, using index that takes as its inputs a list and a value of any type, and returns the index of the first element in the input list that matches the value. If there is no matching element, return -1.
		
		def find_element(p,t):
		    if t not in p:
		        return -1
		    else:
		        return p.index(t)

* Quiz: Pop Quiz

Assume p refers to a list with at least two elements. Which of these code fragments does not change the final value p.
	
	1. x = p.append(3)
	
		p.pop()
	
	2. x = p.pop() y = p.pop() p.append(x) p.append(y)
	
	3. x = p.pop() .append(x)
	
	4. x = p.pop() y = p.pop() p.append(y) p.append(x)

>The result: 3 vs 4

* Quiz Union: 
	 
		p = [1,2,3]
		q = [2,4,6]
		=> union(p,q)
		=> q = [1,2,3,4,6]



Code:

	def union(p,q)
		for e in q:
			if e not in p:
				p.append(e)

* Quiz get all links of page:

We want to append the url to links. This will add that value to the list that links refers to,
keeping track of all the URLs that we found on that page.


	def get_all_links(page):
		links = []
			while True:
				url, endpos = get_next_target(page)
				if url:
					links.append(url)
					page = page[endpos:]
				else:
					break

