Download Link: https://assignmentchef.com/product/solved-solvedprogramming-project-04
<br>
Background

A rotation cipher is one of the simplest, plain-text ciphers, known since at least the time of Julius Caesar. It takes in a plain-text string, and translates it into a new string based on a rotation of the alphabet being used. The basis is a “rotation”, a re-sequencing of an alphabet. Consider the following example. Consider the alphabet being a single string consisting of the lower case English letters as below (shown with each letter’s associated index): a b c d e f g h i j k l m n o p q r s t u v w x y z 0 1 2 3 4 5 6 7 8 9 1 0 1 1 1 2 1 3 1 4 1 5 1 6 1 7 1 8 1 9 2 0 2 1 2 2 2 3 2 4 2 5 then a rotation of 3 means that the first three letters of the alphabet are moved to the end of the sequence, while the other letters move up, as shown below.

Notice that the movement is done one letter at a time. d e f g h i j k l m n o p q r s t u v w x y z a b c A cipher is created by using the rotated alphabet to replace each letter in the original string with its rotated equivalent letter. Using the example above, the word “this” is translated as follows: • the ‘t’ is found at index 19 in the alphabet. The letter in the rotated alphabet is ‘w’

. • the ‘h’ is found at index 7, the rotated letter is ‘k’

• the ‘i’ is found at index 8, the rotated letter is ‘l’

• the ‘s’ is found at index 18, the rotated letter is ‘v’ Thus the string ‘this’ becomes the string ‘wklv’ using a rotation of

3. Project Description / Specification

1) The program should prompt the user for one of three commands:

a) ‘e’ to encode a string

b) ‘d’ to decode a string c) ‘q’ to quit Any other command should raise an error and reprompt.

2) If the command is encode, then the program prompts for a string to encode and a rotation integer in the range of 1-25. The program then returns the encoded string.

a) Important, the program should not encode any letter that is not in the lower case alphabet. Those letters should simply be passed through to the encoded string

3) If the command is decode, then the program should prompt for a string to decode and a plaintext word that appears in the text (decoded string). The output should be the rotation needed to decode the string and the decoded string (text).

a) If the program receives one word that belongs in the decoded string, then the program searches for a rotation that finds that word in the decoded string. That is the proper rotation. Finding that rotation is the goal of the program.

b) If no rotation is found, then the program should indicate this fact.

4) If the command is quit, then the program ends and prints a nice exit message. Deliverables You must use Handin to turn in the file proj04.py – this is your source code solution; be sure to include your section, the date, the project number and comments describing your code. Please be sure to use the specified file name, and save a copy of your proj04.py file to your H: drive as a backup.

Notes and Hints:

You should start with this program, as with all programs, by breaking the program down into parts. Here is some of that breakdown to help you

1. Your program should continuously prompt for a command. Can you write a loop that prompts for one of the three commands ‘d’, ‘e’ or ‘q’ and reports an error if it is not one of those commands?

2. A rotation of an alphabet. Start with a string that consists of the letters a-z in a single string. How can you create a new string of the same length that has a particular rotation? Think of the string slicing operators. What do you need to do to the original string to create a new string of the indicated rotation? What pieces can you concatenate together to make the rotated alphabet?

3. Given two strings, one the lower-case alphabet and one a rotated alphabet, how can you encode a given string? You need to go through each letter of the string to encode, find it in the regular alphabet, remember its location/index in that alphabet, then find the letter in the rotated alphabet at the same index. The python method index is helpful here. It indicates the location of a letter. Thus ‘abcdef’.index(‘c’) should return the value 2, the index of the letter ‘c’. ‘abcdef’.index(‘bcd’) returns 1, where the beginning of the sequence ‘bcd’ occurs. ‘xyz’.index(‘c’) returns -1, as ‘c’ does not occur in the string.

4. When encoding a string, you should check to see if the letter from the original string is in the alphabet. You may use the in operator. ‘a’ in ‘abcde’ returns True. ‘.’ in ‘abcde’ returns False.

5. Decoding is probably the most complicated, best addressed last. You are given a string to decode and a word that occurs in the string. For example, the string ‘this is a test’, when encoded with a rotation of 3, becomes ‘wklv lv d whvw’. When decoding, you provide the encoded string and the word ‘test’.

i. Part 1, can you undo the encoding process if you know the rotation? Here, we find the letter in the rotated alphabet and decode it to the letter in the normal alphabet (the opposite for what we did for encoding).

ii. Part 2, you need to perform Part 1 above on rotations of 1 to 25. If the decoded string contains (remember the in operator) the target string provided (‘test’), this must be the correct decoding. Remember the rotation and output the rotation and the decoded string.

1. If you go through 1-25 rotations and the target string is not found, then there is no decoding of the string possible. Report that. Example Output