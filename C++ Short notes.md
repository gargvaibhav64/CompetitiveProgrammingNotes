# Input

    string s;
    getline( cin , s );
  
# Input and Output from file
    
    freopen("input.txt" , "r" , stdin);
    freopen("output.txt" , "w" , stdout);
    
# Dealing With Numbers

    long long x = 123456789123456789LL; // LL speciied long long
    
    __int128_t is also avaiable.
    
# Modular Arithmetic

    Properites of Modulus:

        (a + b) mod m = (a mod m + b mod m) mod m
        (a − b) mod m = (a mod m − b mod m) mod m
        (a · b) mod m = (a mod m · b mod m) mod m
        
    Example (GeeksforGeeks):
            a = 145785635595363569532135132
            b = 3151635135413512165131321321
            c = 999874455222222200651351351
            m = 1000000007
            Print (a*b*c)%m.

            Method 1:
            First, multiply all the number and then take modulo:
            (a*b*c)%m = (459405448184212290893339835148809
            515332440033400818566717735644307024625348601572) % 
            1000000007
            a*b*c does not fit even in the unsigned long long 
            int due to which system drop some of its most 
            significant digits. Therefore, it gives the wrong answer.
            (a*b*c)%m = 798848767

            Method 2:
            Take modulo at each intermediate steps:
            i = 1
            i = (i*a) % m    // i = 508086243
            i = (i*b) % m    // i = 144702857
            i = (i*c) % m    // i = 798848767
            i = 798848767 
            
    For correct modulus of negative numbers:

        int mod(int a, int m) 
        { 
            return (a%m + m) % m; 
        } 

# Comparing Floating point numbers

    Use:
        
       if (abs(a-b) < 1e-9) {
        // a and b are equal
        }
        
# Shortening Code

    #define REP(i,a,b) for (int i = a; i <= b; i++)
    
# Bit Operations

    x is divisible by 2^k exactly when x & (2^k - 1) == 0
    
    # NOT
        flips all bits
            ~x = - x - 1
        
    # BIT MASKS
    
        K'th bit is one if ( x & ( 1<<k) ) != 0
              
        # Display binary representation of a number
            for (int k = 31; k >= 0; k--) {
                if (x&(1<<k)) cout << "1";
                else cout << "0";
            }
        
        # Some formulas : 
        
            x | (1 << k)        [ Sets the kth bit of x to one ]
            x & ~(1 << k)       [ sets the kth bit of x to zero ]
            x ˆ (1 << k)        [ Inverts the kth bit of x ]
            x & (x − 1)         [ Sets the last one bit of x to zero ]
            x & −x              [ Sets all the one bits to zero, except for the last one bit ]
            x | (x − 1)         [ Inverts all the bits after the last one bit ]
            x & (x − 1) = 0     [ Finds if a positive number x is a power of two exactly ]
