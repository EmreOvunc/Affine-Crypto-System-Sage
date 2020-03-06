# Affine-Crypto-System-Sage

### How affine crypto system works:
The form of the affine cipher is *E(x) = [a.x + b]mod(m)*.

Here, a and b are integers (keys); 
x is the plaintext number to be encrypted. m is 26, because of the use
of a 26 character alphabet in English Alphabet.

Similarly , the decryption form is D(y) = [a -1 .(y-b)]mod(m). a -1 is the inverse of a.

```
For instance, let us encrypt the plain text “EMRE OVUNC”, 
using the key a=3,
b=8.
A=AffineCryptosystem(AlphabeticStrings())
P=A.encoding("EmreOVUNC")
a,b=(3,8)
C=A.enciphering(a,b,P)
A.deciphering(a,b,C)==P
print C
```

### How my codes work:

First of all ,  my codes create affine crypto system and read the plain text from the text file. Then, it generates two keys (key1,key2) and encrypts the plain text -called Cipher (encrypted text)- with using these keys. Next, it writes cipher into another text file.After that, my codes also generates two keys , but these keys are inverse of the key1 and key2. After reading encrypted text , it decrypts all of text and again writes into a another text file , I called DecryptedMessage in my codes.Lastly, I use ranking function to try bruteforce attack with different parameters and write results into another text file.

### Explaining my codes:

* ***def AffineCryptoSystem()***
I tried to use it as a main function.

* ***A=AffineCryptosystem(AlphabeticStrings())***
Creates an affine cryptosystem.

* ***PlainText=A.encoding(Read_TextFile())***
In this line, I read the text file from my desktop with using Read_TextFile() function and encode it. In addition, Read_TextFile() function return lines of file.

* ***key1,key2=GenerateKeys(A)***
I generate key1 and key2 with using GenerateKeys() function. This function create key pairs like a,b=A.random_key() and return them.      

* ***Cipher=Encryption(A,PlainText,key1,key2)***
In this line, I go to the Encryption() function to create cipher text and return Cipher. Also, we use key1 and key2 because of E=A(key1,key2).

* ***key1Inv,key2Inv=GenerateInverseKeys(A,key1,key2)***
Like creating key1 and key2, I inverse key1 and key2 with using  GenerateInverseKeys() function and this function return inverse of key1 and key2.

* ***aInverse,bInverse=A.inverse_key(a,b)***
I generate inverse key of the a and b.

* ***Write_DecryptedText(A,Decryption(A,key1Inv,key2Inv))*** 
This function allows me to write Cipher as a text file.

* ***Ranking_None(A,Cipher)***
***Ranking_Chisquare(A,Cipher)***
***Ranking_Squared(A,Cipher)***
These functions attempt a brute force cryptanalysis of the ciphertext Cipher.

* ***with open ('path/to/my/file','r' or 'w') as TextFile***
In this line, I can read or write a text file for my results. 'r' is read, 'w' is write and 'r+' is read and write.

* ***TextFile.write(Cipher)***
This command allows me to write Cipher into text file which I opened later.

### Input & Output relations
On the one hand, when we take a look inputs, we see that inputs are the plain text like “Hello Cryptography” and it may be one sentence or more sentences. On the other hand, output is encrypted text which is  “TWPPMYJCLHMUJALTC”. We see that the differences between inputs and outputs. This relationship shows us that the algorithm that we can use, works correctly. In addition, you can look the PART FOUR to compare results.
