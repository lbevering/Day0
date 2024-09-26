Python Day 1
email = 'name@somewhere.com'
a = email.split('@')
b = '.'.join(a)
c = b.split('.')
print(c)
----output----
['name', 'somewhere', 'com']
^^^^^^^
line 3 uses common delimiter in order to join so we can split on the next line
print(('.'.join(email.split('@'))).split('.'))       <---   does same thing as above


 #!/usr/bin/env python3
 usr = input('Enter a number\n>> ')
 num = int(usr)
 if num % 5 + num % 3 == False:
    print('fizzbuzz')
 elif num % 3 == False:
    print('fizz')
 elif num % 5 == False:
    print('buzz')
 else:
    print(num)


def test():
  while True:
    user = input("Type 'Pass', 'Break', 'Continue', or 'Return':\n").lower()
    if user == 'pass':
      pass
      print('This is pass.')
    elif user == 'break':
      break
      print('This is break.')
    elif user == 'continue':
      continue
      print('This is continue.')
    elif user == 'return':
      return 'This is return'
    else:
      print('Please choose a valid option.')

list(range(10))
    will print a list of numbers 0-10
list(range(1,10))
    will print a list of numbers 1-10
list(range(0,10,2))
    will print a list of numbers 0-10 counting by 2s 
list(range(0,10,-1))
    will print a list of numbers 0-10 counting backwards from 10


catalog = {'Apex':50,'COD':79.99,'MVP':154.49}
order = [('MVP',5),('COD',2)]
total = 0
for i in order:
    print(catalog[i[0]] * i[1])
    total += catalog[i[0]] * i[1]
print(total)


  PRACTICE EXAM
  1 #!/usr/bin/env python3
  2 
  3 def q1(floatstr):
  4     '''
  5     TLO: 112-SCRPY002, LSA 3,4
  6     Given the floatstr, which is a comma separated string of
  7     floats, return a list with each of the floats in the 
  8     argument as elements in the list.
  9     '''
 10     pass
 11     floatstr = floatstr.split(',')
 12     for f in range(0,len(floatstr)):
 13         floatstr[f] = float(floatstr[f])
 14     return floatstr
 15 def q2(*args):
 16     '''
 17     TLO: 112-SCRPY006, LSA 3
 18     TLO: 112-SCRPY007, LSA 4
 19     Given the variable length argument list, return the average
 20     of all the arguments as a float
 21     '''
 22     return (sum(args) / len(args))
 23     pass
 24 
 25 def q3(lst,n):
 26     '''
 27     TLO: 112-SCRPY004, LSA 3
 28     Given a list (lst) and a number of items (n), return a new 
 29     list containing the last n entries in lst.
 30     '''
 31     newlst = []
 32     while n > 0:
 33         newlst.append(lst[-1*n])
 34         n -= 1
 35     return newlst
 36     pass
 37 
 38 def q4(strng):
 39     '''
 40     TLO: 112-SCRPY004, LSA 1,2
 41     TLO: 112-SCRPY006, LSA 3
 42     Given an input string, return a list containing the ordinal numbers of 
 43     each character in the string in the order found in the input string.
 44     '''
 45     new = []
 46     for s in strng:
 47         n = ord(s)
 48         new.append(n)
 49     return new
 50     pass
 51 
 52 def q5(strng):
 53     '''
 54     TLO: 112-SCRPY002, LSA 1,3
 55     TLO: 112-SCRPY004, LSA 2
 56     Given an input string, return a tuple with each element in the tuple
 57     containing a single word from the input string in order.
 58     '''
 59     strng = strng.split()
 60     strng = tuple(strng)
 61     return strng
 62     pass
 63 
 64 def q6(catalog, order):
 65     '''
 66     TLO: 112-SCRPY007, LSA 2
 67     Given a dictionary (catalog) whose keys are product names and values are product
 68     prices per unit and a list of tuples (order) of product names and quantities,
 69     compute and return the total value of the order.
 70 
 71     Example catalog:
 72     {
 73         'AMD Ryzen 5 5600X': 289.99,
 74         'Intel Core i9-9900K': 363.50,
 75         'AMD Ryzen 9 5900X': 569.99
 76     }
 77 
 78     Example order:
 79     [
 80         ('AMD Ryzen 5 5600X', 5), 
 81         ('Intel Core i9-9900K', 3)
 82     ]
 83 
 84     Example result:
 85     2540.45 
 86 
 87     How the above result was computed:
 88     (289.99 * 5) + (363.50 * 3)
 89     '''
 90     total = 0
 91     print(catalog)
 92     print(order)
 93     numofitems = (len(order))
 94     print(numofitems)
 95     for n in range(0,numofitems):
 96         #grabs the tuple of the order of n 
 97         orde = order[n]
 98         print (orde)
 99         #grabs the name of the item
100         item1 = orde[0]
101         #grabs cost of the item 
102         cost1 = orde[1]
103         ord1p = catalog[item1]
104         print(ord1p)
105         over1p = ord1p * cost1
106         total += over1p
107 
108 
109     return total
110     pass
111 
112 def q7(filename):
113     '''
114     TLO: 112-SCRPY005, LSA 1
115     Given a filename, open the file and return the length of the first line 
116     in the file excluding the line terminator.
117     '''
118     with open(filename, 'r') as fp:
119         line = fp.readlines()[0]
120         line = list(line)
121         num = len(line) - 1
122         return num
123     pass
124 
125 def q8(filename,lst):
126     '''
127     TLO: 112-SCRPY003, LSA 1
128     TLO: 112-SCRPY004, LSA 1,2
129     TLO: 112-SCRPY005, LSA 1
130     Given a filename and a list, write each entry from the list to the file
131     on separate lines until a case-insensitive entry of "stop" is found in 
132     the list. If "stop" is not found in the list, write the entire list to 
133     the file on separate lines.
134     '''
135 
136     with open(filename, 'w') as fp:
137         for n in lst:
138             if n is 'stop':
139                 break
140             fp.write(n + '\n')
141     pass
142 
143 def q9(miltime):
144     '''
145     TLO: 112-SCRPY003, LSA 1
146     Given the military time in the argument miltime, return a string 
147     containing the greeting of the day.
148     0300-1159 "Good Morning"
149     1200-1559 "Good Afternoon"
150     1600-2059 "Good Evening"
151     2100-0259 "Good Night"
152     '''
153     miltime = int(miltime)
154     if miltime >= 300 and miltime < 1200:
155         return 'Good Morning'
156     elif miltime >= 1200 and miltime < 1600:
157         return 'Good Afternoon'
158     elif miltime >= 1600 and miltime < 2100:
159         return 'Good Evening'
160     else:
161         return 'Good Night'
162     pass
163 
164 def q10(numlist):
165     '''
166     TLO: 112-SCRPY003, LSA 1
167     TLO: 112-SCRPY004, LSA 1
168     Given the argument numlist as a list of numbers, return True if all 
169     numbers in the list are NOT negative. If any numbers in the list are
170     negative, return False.
171     '''
172     pos = True
173     for n in numlist:
174         if n < 0:
175             pos = False
176 
177     return pos
178     pass
179 










