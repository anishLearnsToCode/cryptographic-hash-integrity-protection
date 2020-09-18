# Public-Key Cryptography for Both Confidentiality and Source Authentication

Let there be public and private Keys for alice denoted by K_a and k_a respectively and let there 
be public and private keys for Bob denoted as K_b and k_b respectively.

Let M be the plaintext message that Alice wishes to send to Bob with confidentiality and 
authentication. First Alice can compute the Hash of her message as H(M) and then Alice 
will encrypt it with her private key as Enc(H(M), k_a) and store it as 
A = Enc(H(M), k_a)

She can also encrypt her message using Bob's Public Key K_b and create ciphertext as 
C = Enc(M, K_b). Now, she can append the Hash to the ciphertext and send it as C || A.

The attacker eve wishes to understand the contents of the message, she wishes to retrieve M.
She can extract C and H(M) from the message, but she can't decrypt the ciphertext, as that can only
be done using Bob's private key k_b that Eve does not have access to.

Also the Hash function H() is a one way trap-door function and isn't reversible, as many different
plaintext messages map to the same Hash value.

Bob on receiving the message from Alice will be able to retrieve the message M by decrypting the 
ciphertext as P = Dec(C, k_b) with his private key. He can then hash the message H(P) and compare
it with the decrypted Hash value of the Authentication token A with Alice's Public key as 
Dec(A, K_a) and if these values are a match then Bob can confirm that the message was indeed sent 
by Alice.

Let's say that Eve tries to send a message pretending to be Alice, she encrypts message using 
Bob's private key, C = Enc(M, k_b) and computes authentication hash as A = Enc(H(M), k) with some 
key k. Now bob can compute the message as P = Dec(C, k_b) but when he decrypts the authentication 
value with Alice's public key A = Dec(Enc(H(M), k), K_a) this will not be same as the H(M) due 
to different keys and Eve doesn't know the private key of Alice, hence she can never compute
the proper Authentication token A.
