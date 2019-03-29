## Create keyboard buttons

Now that each letter is associated with a hieroglyph, you can start to create your keyboard. You can create a `Button` to do this.

--- task ---
Create a `Button` with the label `a`, which prints the hieroglyph associated with the letter `a`.

```Button["a", {Print[egypt["a"]]}]```

![Simple Button](images/simplebutton.png)

--- /task ---

Great! Now, you need to print more than one letter, and add letters to a word. Instead of using `Print` to print the `Value` each time you press the button, use `AppendTo` to add the `Value` to the end of a list.

Lists start with `{` and end with `}`, and each item is separated by a `,`.

 --- task ---
Create a list called `newWord`. Adapt the `Button` you created in the last task to `AppendTo` the list `newWord` instead of printing. Adapt the `Button` so that it will `Print` the list `newWord`.

```
newWord = {};
Button["a", {AppendTo[newWord, egypt["a"]], Print[newWord]}]
```

 --- /task ---
 
 If you press this button three times, you should get this output:

![Button Output](images/buttonoutput.png)

