# Custom String Builder

### Requirements 

Implement a custom string builder class with the necessary internal data structure(s) for string manipulation.
Include the following methods in your class:

- Length method that returns the current length of the string being built
- Append method, which appends the given string to the end of the current string
- InsertAt method, which inserts the given string at the specified index in the current string
- RemoveDuplicates method, which removes duplicate characters from the current string, leaving first occurrences only
- RemoveWhitespace method, which removes all whitespace characters from the current string
- ToCase method, which formats the current string to specified case ( Pascal, Camel, Snake, Kebab )
- Split method, which splits the current string into chunks of given size
- Shuffle method, which randomly shuffles the characters in the current string
- IsBlank method, which checks whether the current string is null, empty or only whitespace characters
- OnBlank method, which returns the current value or the given string if the current value is blank
	
### Expected result

The resulting application should be successfully compiled and executed.

### Additional notes

- DO NOT use the built-in StringBuilder class or any other existing string manipulation libraries
- Ensure that your code follows established coding conventions and is written in a readable and clean manner
- Be creative and think about methods that would be useful and beneficial in different scenarios