## Creating a Keyboard

Now that each letter is associated with a hieroglyph, we can start to build our keyboard. The best way to do this is to build some Buttons.


--- task ---
Create a button with the label `a`, which prints the hieroglyph associated with the letter `a`.

```Button["a", {Print[egypt["a"]]}]```

![Simple Button](images/simplebutton.png)

--- /task ---

Great! But we don't just want to print one letter. We want to be able to add letters to a word. Instead of using `Print` to print the Value each time we press the button, let's use `AppendTo` to add the Value to the end of a list.

 --- task ---
Create a list called `newWord`. Adapt the button you created in the last task to `AppendTo` the list `newWord` instead of printing. Adapt the button to `Print` the list `newWord`.

```
newWord = {};
Button["a", {AppendTo[newWord, egypt["a"]], Print[newWord]}]
```

 --- /task ---
 
 If you press this button three times, you should get this output:

![Button Output](images/buttonoutput.png)

We want to be able to add any letter to the word. We could make each button individually, like we did in the last task. Or, we could iterate over the list of Keys using the `Table` function.
Let's look at an example of Table. Try to work out what the function is doing.

![Example of Table function](images/tableexample.png.png)

`Table` works a lot like a for loop in other programming languages. For `i` in the list `{0, 10, 20, 30}`, add 5 to i. We can use `Table` to create buttons for every Key in our `Association`.

You can get a list of all the Keys using `Keys[egypt]`

Instead of running `"a"` through the `Association` to return the hieroglyph for `"a"`, this time we want to be able to press a button for any letter, and have the hieroglyph for that letter added to the list `newWord`. In order to do this, we need to use an iterator, like `i` instead of a specific letter.

We also need to tell the `Table` function that we want to use the iterator `i` as the input. We can do this using `With[{i=i}]`.


--- task ---
Use `Table` to build a list of `Button`s. Each button should have the label of the Key in the `Association`, and should add the Value associated with that Key to the list `newWord`.

```
newWord = {};
Table[With[{i = i}, 
  Button[i, {AppendTo[newWord, egypt[i]], Print[newWord]}]], {i, 
  Keys[egypt]}]
```
  
--- /task ---

You might notice that every time you press the button, the new output appears underneath the old output. It would be better to replace the old output with the new output each time you press the button.

We can do this using `Dynamic`. `Dynamic` displays the dynamically updated value, so each time we reevaluate the code by pressing the button, `Dynamic` will update to the new value.

We can also get rid of the `{}` and `,` in the list `newWord`, and in the `Table` of buttons, by using `Row`.

--- task ---
Make `newWord` print as a row using `Row`.
Make the `Table` of buttons print as a row using `Row`.
Use `Dynamic` to replace the keyboard output each time you press a button. 

```
word = {};
Row[Table[
  With[{i = i}, Button[i, {AppendTo[word, egypt[i]]}]], {i, 
   Keys[egypt]}]]
Dynamic[Row[word]]
```
---/task---
