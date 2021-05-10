# Week 1 Challenge Questions

### Time Complexity
Explain what each of these mean as clearly as you can. Use examples whenever possible.

- O(1) 
`Constant, it will always take the same amount of time, for example printing the first element of an array`

- O(log n)
`Logarithmic, the time will approach constant time as the input approaches infinity, for example searching a value in a sorted binary tree, where at each step half the tree is discarded`

- O(n)
`Linear, the time will increase at a constant rate as input approaches infinity, for example printing all elements of an array`

- O(n²)
`Quadratic, the time will increase exponentially as input approaches infinity, for example a nested for loop comparing values in an array`

- O(n log n)
`Linearithmic, the time will approach linearity as input approaches infinity, for example a logarithmic function nested inside a linear one,  `

### Write a quick plain English algorithm for the following case:

(Linked List)—`insert(val)`
1. Set previous tail.next to new node
2. Set new tail.value to val
3. Set new tail.next to null

(Example, BST) —`search(value)` 
 1. Create new node with value
 2. If tree is empty, assign root = new node
 3. Else, assign current node = root
 4. ...
 
## Bonus Questions

### What are the benefits of pair programming? What about drawbacks?
`Pair programming allows one to focus on either the actual writing, or the more abstract pseudocode part, minimizing syntax errors and allowing an exchange of knowledge between the two programmers. As a drawback keeping both programmers engaged can be challenging if there is a vast skill-gap, and from a company's perspective it can be more expensive and not worth the RoI.`

### When using Slack at Code Chrysalis, what is the meaning of these emojis?
- ✅ `Issue is resolved`
- 🎉 `Issue was resolved by the same person who asked`
- 👀 `Issue has been noticed`