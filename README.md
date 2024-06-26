What are Palindromes?
A palindrome is a word, phrase, or sequence that reads the same backwards as forwards. They can be both numeric and characters. For instance – 

Example
Radar, Kayak, 12321,1221

All above are examples of palindrome as they are same when read forwards/backwards
Checking for Palindrome
Write a program to Check whether a String is Palindrome or not in python
Methods discussed
Method 1: Using String Slicing
Method 2: Matching ith character from front-back
Method 3: Matching ith character from front-back (Updated)
Method 4: Inbuilt function
Method 5: Building using arithmetic
Method 6: Building using flag
Method 7: Negative Traversal in loop
Program to Check given String is Palindrome or Not in Python
Method 1
This method uses negative slicing to generate reverse of string

Run
# Write a program to check whether a string is palindrome or not in python
input_string = 'civic'
rev = input_string[::-1]

if input_string == rev:
    print(rev + " is Palindrome")
else:
    print(rev + " is not Palindrome")
Output
civic is Palindrome
Method 2 (Matching ith character from front-back)
For string check, if each i-th character from the front is the same as i-th character from back or not.

If yes then its a palindrome

Python Code
Run
def isPalindrome(input_str):

    # check if input_str[i] is same as input_str[len(str) - i - 1]
    # for each char in string
    for i in range(0, len(input_str)):

        # Essentially, what is being checked isif i-th character is
        # equal to i-th character from the end or not
        if input_str[i] != input_str[len(input_str) - i - 1]:
            return False

    return True

input_str = "civic"

print("Palindrome") if isPalindrome(input_str) else print("Not Palindrome")
Output
civic is Palindrome
Related Pages
Juggling algorithm for array rotation
 
Balanced Parenthesis Problem
 
Toggle each character in a string

Find the ASCII value of a character

Length of the string without using strlen() function


Method 3 (Matching ith character from front-back, updated)
It’s very similar to the previous method, with one difference that –

Rather than checking ith character from the front is the same as the ith character from the back for the whole string.

We just check for the first half of the string, since, if the string is Palindrome. The first half and second half when read backwards will anyways be the same.

Python Code
Run
def isPalindrome(input_str):
    # Run loop from 0 to len/2
    mid = int(len(input_str) / 2)
    for i in range(0, mid):

        # Essentially, what is being checked isif i-th character is
        # equal to i-th character from the end or not
        if input_str[i] != input_str[len(input_str) - i - 1]:
            return False

    return True


input_str = "civic"

print("Palindrome") if isPalindrome(input_str) else print("Not Palindrome")
Output
civic is Palindrome
Method 4 (inbuilt function)
We will use inbuilt reversed function to do it in this method

Run
# main function
string = "civic"

reverse = ''.join(reversed(string))

print(string + " is: ", end="")
print("Palindrome") if string == reverse else print("Not Palindrome")
Output
civic is: Palindrome
Method 5 (Building reverse using arithmetic)
We build the reverse using arithmetic here

Run
input = "civic"
# this will automatically generate reverse
rev = ""
for ch in input:
    rev = ch + rev

print(input + " is : ", end="")
print("Palindrome") if input == rev else print("Not Palindrome")

print("string: " + input)
print("rev: " + rev)
Output
civic is : Palindrome
string: civic
rev: civic
Method 6 (Building reverse using flag)
We build the reverse using flag here

Run
input = "civic"

j = -1
flag = 0
for char in input:
    # char starts from index 0
    # string[j] forces to read from end
    # bcz negative index are read from end
    if char != input[j]:
        flag = 1
        break
    j = j - 1

print(input + " is : ", end="")
print("Not Palindrome") if flag else print("Palindrome")
Output
civic is : Palindrome
Method 7 (Negative traversal in Loop)
We build the reverse using Negative traversal in Loop

Run
input = "civic"
n = len(input)
revlist = []

for i in range(n - 1, -1, -1):
    revlist.append(input[i])

rev = "".join(revlist)

print(input + " is: ", end="")
if input == rev:
    print("Palindrome")
else:
    print("Not Palindrome")
Output
civic is : Palindrome
