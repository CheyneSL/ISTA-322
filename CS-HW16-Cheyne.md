# C# Homework 16

---

**Cheyne Lowery**

**March 02, 2021**

**CS-HW16-Cheyne.md**

---

- Indexers provide access to items that contain multiple values (properties for arrays)
- int stores its value as a sequence of 32 bits
- Specify integer constants using binary notation, indicated by a prefix of: **0b0** (any bits unspecified are defaulted to **0**
- Always declare an int constant as a **Type<uint>**
- Hexadecimal values are prefixed with **0x0**
- To display the binary representation to number, use the method **Convert.ToString()** on an integer
- The **Bitwise NOT** operator is **~**. This flips the binary values in a binary representation
- The **left-shift** operator is **<<**. Shifts all binary values to the left and the far left bits are discarded
- The **OR** operator is **|**. Returns binary representation where all **1s** are true in **either** of two numbers
- The **AND** operator is **&**. Returns binary representation where all **1s** are true in **both** of two numbers.
- The **XOR** operator is **^**. Returns binary representation where **1s** are true and **unique**.

1. Give five examples of the five bitwise operators using valid c# code:

```c#
	//Fields
	int integer = 187;
	int integer2 = 123;
	string intbase2 = Convert.ToString(187, 2);
	string int2base2 = Convert.ToString(123, 2);
	
	//Bitwise NOT (-188)
	int NOTint = (~integer);
	
	//Bitwise Left Shift (748)
	int leftShiftInt = integer << 2;
	
	//Bitwise OR (251)
	int ORint = integer | integer2;
	
	//Bitwise AND (59)
	int ANDint = integer & integer2;
	
	//Bitwise XOR (192)
	int XORint = integer ^ integer2;
```

2. C# *does* implement the *right-shift* operator. An example using valid c# code:

```c#
    int i = 46;
    string iBase2 = Convert.ToString(i, 2);

    int j = i >> 2;
    string jBase2 = Convert.ToString(j, 2);

    Console.WriteLine($"The value of i is {i}, {iBase2}.");
    Console.WriteLine($"The value of j is {j}, {jBase2}.");
    Console.WriteLine("All trailing zeroes are dropped in the 8-bit binary conversion."); 
```

3. The following code iterates through a binary array from right to left, by starting at the end using var *index* which is set to the length of the binary array. To iterate, it left shifts. The value of *bits* is checks to see if it is equal to the value of the current index using the *&* bitwise operator. This is equivalent to a *decrementing for loop* using an *equality operator* - would be implemented *ONLY* under the indexer accessor, *get* as there is no compound operator and thus does not specify and implicit *set*.

```c#
	bits & (1 << index)
```

4. The following code uses *implicit* indexer get and set accessors. It iterates from right to left the binary array, and using the *OR* bitwise operator, it sets the value of each index to the value of *bits*.

```c#
	bits |= (1 << index);
```

5. The follwing code iterates from right to left, using the legth of the binary array. It uses a compound assignment operator which indicates implicit *indexer get and set accessors*, and evaluates whether the *bits* variable and the index value are the same using the *&* bitwise operator. If they boolean evaluation evaluates to true, the value of the index is automatically set to the value of *bits*.

```c#
	bits &= (1 << index);
```

6. C# interprets the *bits[]* as an array of booleans indicative the binary representation of a value. It declares a variable named *peak* of <t> *bool*, and stores true of the value of index, *n* in the array, *bits* contains *1*, and false if the value of *n* is *0*.

```c#
	bool peak = bits[n];
```

7. C# accesses the index, *n* of the binary array, *bits*, and sets the value to *true* which has a literal value of *1*.

```c#
	bits[n] = true;
```

8. C# accesses the index, *n* of the binary array, *bits*, and sets the value to *false* which has a literal value of *0*.

```c#
	bits[n] = false;
```

9. Assuming that users were assigned read, write, and execute permissions according to this scheme: **read = 1**, **write = 2**, and **execute = 4**. I would interpret the follwing permissions in C# as combined values of the permission scheme based on the total value of the permissions added together. If a user had permissions equal to 7, he would have read(1) + write(2) + execute(4) = 7. If a user had permissions equal to 3, he would have read(1) + write(2) = 3.

  - (a) permission = 0
  - (b) permission = 1
  - (c) permission = 2
  - (d) permission = 3
  - (e) permission = 4
  - (f) permission = 5
  - (g) permission = 6
  - (h) permission = 7
  
 10. To answer the previous question by converting them to binary permissions, I would store each permission and permission scheme in new variables by converting them to their binary representations. I would then compare the binary representations to their literal values to derive the permission scheme. This tells me that literal values are equivalent to their binary representations as far as the computer is concerned.
			
			
			