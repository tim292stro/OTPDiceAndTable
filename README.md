This is a simple one-pager PDF, based on the youtube video: https://www.youtube.com/watch?v=QRa_zzQOEe8
  
# Usage:
* Get a 6-sided Die
* Throw the die twice for each character of a One-Time-Pad
* Record the character that appears for the combination of the two throws
* Rinse-repeat until you have your key length
* Put the die back where you got it
* Exchange the OTP with the other person who you are conversing with
  
# Encrypting:
* Take a character from your plain-text, find the row on the left-most column
* Take a character from the OTP stream, find the colum at the top ("Key In")
* Where the row and column intersect, write the character in your cypher-text out
* Rinse-repeat until you have converted all the plain-text into cypher-text
* If you still have OTP characters left, append them to the end of the cyphertext to mask the length of the message
* Destroy that OTP stream, send the message (in that order)
  
# Decrypting:
* Take a letter from the OTP stream, find the column at the top ("Key In")
* Take the letter from the cypher-text, find the row for that character in that OTP character's column
* Follow the row for the cypher-text character to the letter on the plain-text out column to the right, write down the character in the plain-text out
* Where the cypher-text characters match the OTP stream's characters, you'll find the end of the message, and may discard the rest of the letters
* Destroy that OTP and the message... OR (see next section)
  
# Bonus skill, for plausible denyability:
* Create a new plaintext message, unrelated to the decrypted message
* Generate a new "OTP stream" finding the row for each plain-text character:
 * Find the column on that plain-text character's row where the cipher character is
 * Record the OTP character at the top row of that column ("Key In") to the spoofed OTP
 * Rinse repeat to the end of message, fill the rest of the OTP with the cipher text following the end of your new message
 * Fully destroy the true OPT and true message
 * Retain the false OTP and false message, make a weak attempt to conceal the false OTP and false message
