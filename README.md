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


long long int power(long long int base, long long int exp, long long int mod) {
    long long int result = 1;
    base = base % mod;
    while (exp > 0) {
        if (exp % 2 == 1)  
            result = (result * base) % mod;
        exp = exp >> 1;    
        base = (base * base) % mod;
    }
    return result;
}

int main() {
    long long int P, G, a, b, x, y, ka, kb;

    printf("\n***** Diffie-Hellman Key Exchange Algorithm *****\n\n");

   
    printf("Enter the value of P : ");
    scanf("%lld", &P);

    
    printf("Enter the value of G (primitive root modulo P): ");
    scanf("%lld", &G);

    
    a = 4;  // Alice's private key
    b = 3;  // Bob's private key

    printf("\nPrivate key for Alice: %lld", a);
    printf("\nPrivate key for Bob: %lld\n", b);

    // Public keys generated
    x = power(G, a, P);  // Alice sends this to Bob
    y = power(G, b, P);  // Bob sends this to Alice

    // Shared secret keys computed
    ka = power(y, a, P); // Alice computes secret key
    kb = power(x, b, P); // Bob computes secret key

    printf("\nShared secret key for Alice: %lld", ka);
    printf("\nShared secret key for Bob: %lld\n", kb);

    return 0;
}
```

## Output:

![Screenshot 2025-05-06 143834](https://github.com/user-attachments/assets/52c8c04d-5f81-4a44-9dd1-dc3f699fab42)



## Result:
  The program is executed successfully

