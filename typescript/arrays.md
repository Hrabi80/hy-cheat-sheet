# TypeScript Arrays Cheat Sheet
## Array methods
Method | Description      
--- | ---
`pop()` | Removes the last element of the array and return that element
`concat()` | 	Joins two arrays and returns the combined result
`indexOf()`| Returns the index of the first match of a value in the array (-1 if not found)
`lastIndexOf()` | Returns the last index of an element in the array
`copyWithin()` | Copies a sequence of elements within the array
`fill()` | Fills the array with a static value from the provided start index to the end index
`shift()` | Removes and returns the first element of the array
`unshift()` | Adds one or more elements to the beginning of the array
`slice()` | Adds or removes elements from the array
`include()` | Checks whether the array contains a certain element
`join()` | Joins all elements of the array into a string

## Examples

```typescript
    var fruits: Array<string> = ['Apple', 'Orange', 'Banana'];
```
### concat
```typescript
    fruits=fruits.concat(['Fig','Mango'])
```
