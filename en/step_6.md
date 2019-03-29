## Improve the interface

You can use `Grid` to make a nice keyboard layout for your project. Here is an example of `Grid`:

![Grid](images/Grid.png)

`Grid` is made up of a list of lists, where each list becomes a row in the grid.

--- task --- 
Make a `Grid` with three rows. The first row should be the `Dynamic` output of `newWord`. The second row should be the `Table` of buttons which make the keyboard. The third row should be the "Clear" and "Delete" buttons you made in the previous step.

Draw a box around the `Grid` by setting `Frame` to `True`.

--- hints ---
--- hint ---
The basic structure of a `Grid` with a frame looks like this, with the list of lists defining the rows of the grid.
```
Grid[{{},{},{}}, Frame -> True]
```
--- /hint ---
--- hint ---
Use this code for the rows:

```
Dynamic[Row[newWord]]
```

```
Row[Table[With[{i = i}, Button[i, AppendTo[newWord, egypt[[Key[i]]]]]], {i, Keys[egypt]}]]
```

```
Row[Table[With[{i = i}, Button[i, AppendTo[newWord, egypt[[Key[i]]]]]], {i, Keys[egypt]}]]
```
--- /hint ---
--- hint ---
This is the finished code for the grid:

```
newWord = {};
Grid[{
  {Dynamic[Row[newWord]]},
  {Row[Table[With[{i = i}, Button[i, AppendTo[newWord, egypt[[Key[i]]]]]], {i, Keys[egypt]}]]},
  {Button["Clear", newWord = {}], Button["Delete", newWord = Drop[newWord, -1]]}
  }, Frame -> True]

```
--- /hint ---
--- /hints ---

---/task ---

The keyboard works! Now, add a title and improve the placement of the "Clear" and "Delete" buttons to make the keyboard look nicer and easier to use.

You can use `SpanFromLeft` to span elements across the `Grid`.

![Grid Span](images/GridSpan.png)

In the `Grid`, the first two rows have one item, and the third row has two items. If you add `SpanFromLeft` to the first two rows, and add a third, blank, element to the third row, then the "Clear" and "Delete" buttons will line up on the left.

You can also add a row at the top of the `Grid` with a title. You can use `Text` and `Style` to make the title look like text and print in a large font size.

---task---
+ Use `SpanFromLeft` to shift the "Clear" and "Delete" buttons to the left
+ Add a title to the top of the `Grid`
+ Replace all the code you have written (except for the association `egypt`) with your new code

The code will look like this:

```
newWord = {};
Grid[{
  {Text[Style["Hieroglyphics Keyboard", 24]], SpanFromLeft},
  {Dynamic[Row[newWord]], SpanFromLeft},
  {Row[Table[With[{i = i}, Button[i, AppendTo[newWord, egypt[[Key[i]]]]]], {i, Keys[egypt]}]], SpanFromLeft},
  {Button["Clear", newWord = {}], Button["Delete", newWord = Drop[newWord, -1]], ""}
  }, Frame -> True]
```
---/task---

![Complete project](images/Complete.png)
