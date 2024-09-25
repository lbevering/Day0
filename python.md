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













