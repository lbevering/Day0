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

