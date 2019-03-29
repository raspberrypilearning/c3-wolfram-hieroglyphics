## Create the keyboard

In the last step, we created a `Button` for the letter `"a"`.

Now, you need to be able to add any letter to the word. You could make each button individually, like in the last step, or you could use the `Table` function to repeat an action over every `Key`.

Look at an example of `Table`. Do you see what the function is doing?

![Example of Table function](images/tableexample.png)

If you are familiar with other programming languages, `Table` works a lot like a `for` loop in many languages. For example, you might want to add 5 to every number in a list. `Table` does this by taking two arguments: the action, and the list. So, to add 5 to every number in a list, you would type: `Table[i+5, {i, {0,10,20,30}}]`. This code would return: `{5, 15, 25, 35}`.

You can use `Table` to create buttons for every `Key` in your `Association`.

Type `Keys[egypt]` to get a list of all of the `Keys`. This will return all the letters of the alphabet which you have used as `Keys`.

Instead of running `"a"` through the `Association` to return the hieroglyph for `"a"`, you will now write a code so that you can press a button for any letter, and the hieroglyph for that letter will be added to the list `newWord`. To do this, you need to use a dummy variable, like `i`, instead of a letter. Then, each time you press a button, the `Value` of that button will replace the dummy variable `i`.

You also need to tell the `Table` function that you want to use whatever replaces the dummy `i` when you press a button as the input. You can use `With[{i=i}]` to do this.

--- task ---
Use `Table` to make a list of `Button`s. Each `Button` should have the label of the `Key` in the `Association`, and should add the `Value` associated with that `Key` to the list `newWord`. You can use the following code:

```
newWord = {};
Table[With[{i = i},
Button[i, {AppendTo[newWord, egypt[i]], Print[newWord]}]],
{i, Keys[egypt]}]
``` 
--- /task ---

You might notice that every time you press the button, the new output appears underneath the old output. It would be better to replace the old output with the new output when you press the button.

You can use `Dynamic` to do this. `Dynamic` displays the updated value, so every time you press the button and rerun the code, `Dynamic` will display the new value and replace the old value.

To improve the look of the output, put the output into a `Row`. This will remove the `{}` and `,` in the list `newWord` and in the `Table` of buttons.

--- task ---

+ Use `Row` to make `newWord` print as a row
+ Use `Row` to make the `Table` of buttons print as a row
+ Use `Dynamic` to replace the keyboard output each time you press a button
+ Replace your code from the previous task with your new code

You can use the following code:

```
newWord = {};
Row[Table[
  With[{i = i}, Button[i, {AppendTo[newWord, egypt[i]]}]], {i, 
   Keys[egypt]}]]
Dynamic[Row[newWord]]
```
---/task---
