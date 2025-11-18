# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```
#include <stdio.h> 
#include <math.h> 
 
long long power(long long base, long long exp, long long mod) { 
    long long result = 1; 
    for (int i = 0; i < exp; i++) { 
        result = (result * base) % mod; 
    } 
    return result; 
} 
 
int main() { 
    long long p, g, a, b; 
    long long A, B, secretA, secretB; 
 
    printf ("Enter a prime number (p): "); 
    scanf("%lld", &p); 
    printf ("Enter a primi ve root of %lld (g): ", p); 
    scanf("%lld", &g); 
    printf ("Enter First party's private key: "); 
    scanf("%lld", &a); 
    printf ("Enter Second party's private key: "); 
    scanf("%lld", &b); 
 
    A = power(g, a, p); 
    B = power(g, b, p); 
    secretA = power(B, a, p); 
    secretB = power(A, b, p); 
 
    printf ("\nPublicly known values: p = %lld, g = %lld\n", p, g); 
    printf ("First party's Private Key: %lld\n", a); 
    printf ("Second party's Private Key: %lld\n", b); 
    printf ("\nAlice's Public Key: %lld\n", A); 
    printf ("Bob's Public Key: %lld\n", B); 
    printf ("\nShared Secret Key (Alice): %lld\n", secretA); 
    printf ("Shared Secret Key (Bob): %lld\n", secretB); 
 
    if (secretA == secretB) 
        printf ("\nKey Exchange Successful! Shared secret is same.\n"); 
    else 
        printf ("\nError: Shared secrets do not match.\n"); 
 
    return 0; 
}
```


## Output:
<img width="628" height="601" alt="image" src="https://github.com/user-attachments/assets/2bb037a0-7dda-4b92-b7ca-d60a6ea74fbf" />



## Result:
  The program is executed successfully

