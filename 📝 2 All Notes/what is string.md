---
tags:
  - dsa
  - string
status: 🟩
---

2026-01-27        10:25

---
# What is Title?

- string is combination of characters.

```cpp
#include<iostream>
using namespace std;
int main(){
	string s = "Abir";
	cout << s << endl;
	cout << s.size() << endl;
	cout << s.length() << endl;
	return 0;
}
```

## Take input in string

```cpp
#include<iostream>
using namespace std;
int main(){
	string s;
	cin >> s;
	getline(cin, s);
	return 0;
}
```

## String Operations

```cpp
//* String operations
string s1 = "Abir";
string s2 = "Bhattacharjee";

//* Add string
string s3 = s1 + " " + s2;
cout << s3 << endl;

//* Push characters
s3.push_back('!');
cout << s3 << endl;

//* Pop characters
s3.pop_back();
cout << s3 << endl;
```

---
