## Clearing the Output and Deleting the Last Value

What if we want to clear the whole word, or if we want to delete the last hieroglyph which was added to the word?
Let's make a `Button` to empty the list `newWord`. To empty the list, we can set `newWord` to be an empty list, just like we did to initialise the variable at the start.

--- task ---
Create a `Button` which sets `newWord` to be an empty list.

```
Button["Clear", word = {}]
```
--- /task ---

Let's also make a `Button` which deletes the last hieroglyph which was added to `newWord`.
In order to delete the last character inserted into the list, we can use the function `Drop`. `Drop` takes two arguments, the list, and the elements in the list we want to drop.
To delete the first two elements of the list, we would `Drop[{a, b, c, d, e, f}, 2]`, which would give us the list `{c, d, e, f}`. However, we want to drop the last element of the list. For this, we use `-1`. `Drop[{a, b, c, d, e, f}, -1]` returns the list `{a, b, c, d, e}`.
 
--- task ---
Use the function `Drop` to create a `Button` which deletes the last hieroglyph in `newWord`.

```
Button["Delete", word = Drop[word, -1]]
```
 --- /task ---
