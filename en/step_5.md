## How to clear the output and delete the last value

What if you want to clear the whole word, or delete the last hieroglyph which was added to the word?
You can make a `Button` to empty the list `newWord`. To empty the list, you can set `newWord` to be an empty list, like you did to initialise the variable at the start.

--- task ---
Create a `Button` which sets `newWord` to be an empty list. You can use the following line of code:

```
Button["Clear", newWord = {}]
```
--- /task ---

Next, make a `Button` which deletes the last hieroglyph that was added to `newWord`.
You can use the function `Drop` to delete the last character that was added to the list. `Drop` takes two arguments: the list, and the elements in the list that you want to remove.
To delete the first two elements of the list, you would type `Drop[{a, b, c, d, e, f}, 2]`, which would give you the list `{c, d, e, f}`. However, you want to drop the last element of the list. For this, you use `-1`. If you type `Drop[{a, b, c, d, e, f}, -1]`, you get the list `{a, b, c, d, e}`.
 
--- task ---
Use the function `Drop` to create a `Button` which deletes the last hieroglyph in `newWord`:

```
Button["Delete", newWord = Drop[newWord, -1]]
```
 --- /task ---
