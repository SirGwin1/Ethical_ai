Exercise 2: Strengthening Through Variations
1. Modify your palindrome function to:

    Ignore spaces and punctuation.

    Be case-insensitive.

    Return the position where the string stops being a palindrome (if not one).
Ans: 
def palindrome_checker(s):
    #modifying string to be case insensitive
    s = s.lower()
    #modification of string to ignore spaces
    s = s.replace(" ", "")
    #reversing item to convert it to a palindrome
    return s == s[::-1]
    
#test_cases
print(palindrome_checker("Racecar"))
print(palindrome_checker("hello"))
print(palindrome_checker("A man a plan a canal Panama"))

2. After your first attempt, ask AI:
Ans:
heres the modifications AI provided to my code

def palindrome_checker(s):
    # Step 1: Clean the string
    clean_chars = []
    for char in s.lower():
        if char.isalnum():
            clean_chars.append(char)
    
    clean_s = ''.join(clean_chars)
    
    # Step 2: Check if palindrome and find fail position
    length = len(clean_s)
    for i in range(length // 2):  # Only need to check half
        if clean_s[i] != clean_s[length - 1 - i]:
            return False, i  # Return position where it fails
    
    return True, -1  # -1 means it's a palindrome

3. Reflect on what AI added that you didn't consider initially.

AI did some modification on my code and added certain built-in functions like isalnum() and "".join(). Thus heres my variation

def palindrome_checker(s):
    #string processing
    processeed_s = ''.join(char.lower() for char in s if char.isalnum())
    
    # palindrome_check
    for i in range(len(processeed_s) // 2):
        if processeed_s[i] != processeed_s[-(i+1)]:
            return False, i 
    
    return True, -1

print(palindrome_checker("hello"))
print(palindrome_checker("Racecar"))
print(palindrome_checker("A man a plan a canal Panama"))