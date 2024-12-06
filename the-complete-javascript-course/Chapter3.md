# Chapter 3: Intermediate Skills with JS

## Arrays, Objects, and Manipulating Data

### Strings

- JS does not give errors when accessing index out of bounds. It just determines the value as **undefined**.
- `'3' + 5` is a string '35', even if order change.
- `'3' + 5 - 6` is a number 29.
- **indexOf** returns the index of a substring, else -1.
- **split** removes regex and splits the rest into a list.
- **includes** checks if a letter is in string or not.
- **replace** swaps first instance while **replaceAll** swaps every instance.
- **slice** slices a string. If given 1 arg, it gives the string from that index up till the end.
- The best way to use regex is to use the help of ChatGPT. This is used in matching strings.

### Arrays
- **push** adds element to the end
- **pop** returns the value and removes it
- **includes** returns whether element is in array or not
- **indexOf** returns -1 if element is not there
- **join** like python's join
- **reverse** reverses an array in place
- **sort** sorts the array in place
- **slice**
- **concat**

### Dictionaries or Objects

- Even with const, dictionaries could have their contents altered as long as we are only editing data inside.
- We access keys as square brackets and a string `bio['age']` inside or a point and an attribute `bio.age`, and this is quite important.
- To check whether key in dictionary: `'key_name' in dictionary`
- `delete key` deletes a key value pair from the dictionary
- Dictionaries do not have an indexing system
- Accessing keys that are not in dictionary will give you undefined.
  
## Scope, Closures, and Writing Modular code

## Error Handling and Debugging