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
In order to delete the last character inserted into the list, we can use the function `Drop`.
 
--- task ---
Use the function `Drop` to create a `Button` which deletes the last hieroglyph in `newWord`.

```
Button["Delete", word = Drop[word, -1]]
```

 --- /task ---
