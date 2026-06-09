# ccn - Extension Classes
Copyright 2026 McPherran  
[License](https://github.com/McPherran/Programming-Language/edit/main/LICENSE)

C++ class syntax is replaced by "class <type>" where type is the type (e.g.
data/struct) that is used as the type of the first arg for all member functions.
"class <type>" can be used in the same nanmespace in multiple source files. This
is a form of extension methods (partial classes). Example:

## C++

	class example_type
	{
		char a;
		std::string str;

	public:

		example_member_function(char b)
		{
			str.append(a);
		}
	}

## ccn

	struct example_type
	{
		int a;
		std::string str;
	}

	// example_type is first arg of all functions contained in the class braces.
	// The first arg is accessed using '.'
	class example_type
	{
		example_member_function(char b)
		{
			.str.append(.a);
			.str.append(b);
		}
	}

	
