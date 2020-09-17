# Password Storage Using Hash Functions

### Identify a real-world examples in which hash functions are being used, explain the use of the hash functions in the example context, and provide an online article/resource that corroborates with your answer.

A Hash Function is a mathematical function that converts a numerical value into another 
compressed numeric value. The input value for the hash functions can be of arbitrary length, but the 
output text that it will produce will always be  of fixed length.

__Properties of Hash Functions:__

1. Compressed output
1. Fixed Length Output
1. Pre-Image Resistance
1. Second pre-Image Resistance
1. Collision Resistance

Due to the pre-Image resistance and collision resistance property, the hash functions are ideal to 
use for storing the passwords. Therefore, the values that are stored in the database are the user-Id 
in its original form and the hash value of the password. Therefore, whenever you enter the Id 
and password into a system, it searches for the user-Id, if available, it matches the hash values 
of the entered password and the password that is already there in the database. If both are the 
same, then access is granted.

Link: https://www.includehelp.com/cryptography/applications-of-hash-function.aspx

### Explain how critical the hash requirements are in the real-world example you provided for each of the following requirements: pseudo-randomness, avalanche effect, preimage resistance, weak collision resistance, and strong collision resistance.

In password storage the resistance to preimage attack is of utmost importance, as deterring the 
pre-image (actual password) given a hashcode should be something that should be computationally 
unfeasible and and other features of the cryptographic hash such as pseudo-randomness and 
weak collision resistance are of less importance. 

The avalanche effect is of very high importance as that adds an obfuscating and diffusion quality 
to the algorithm where changing even a single character in the message changes more than half of 
the hashcode, this makes discerning a relation between the message and encipherment function 
very difficult and protects the passwords.
