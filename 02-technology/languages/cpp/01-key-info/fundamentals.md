# Fundamental Key Information

This file is a collection of things I consider key information to know for C++ fundamentals.

<br>

---

<br>

## Using namespace std

This isn't just personal preference; It comes with more drawbacks than benefits. The little time you save typing `std::` is not worth the risk. 

```cpp
#include <iostream>
using namespace std; // BAD!

int main() {
	string message = "This is lazy and problematic";
	return 0;
}
```

Reducing the scope to the features you only need (such as `using std::string` for example) is better, but still not advised. 

```cpp
#include <iostream>

using std::string; // BETTER (STILL NOT GREAT)

int main() {
	string message = "This is better";
	return 0;
}
```

Recommended:

```cpp
#include <iostream>

int main() {
	std::string message = "This is recommended"; // BEST
	return 0;
}
```

<br>

---

<br>

## Hex Table

|Hex|Binary|Decimal|
|---|---|---|
|0|0000|0|
|1|0001|1|
|2|0010|2|
|3|0011|3|
|4|0100|4|
|5|0101|5|
|6|0110|6|
|7|0111|7|
|8|1000|8|
|9|1001|9|
|A|1010|10|
|B|1011|11|
|C|1100|12|
|D|1101|13|
|E|1110|14|
|F|1111|15|
