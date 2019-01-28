## Associating Hieroglyphs with Letters

In order to represent English letters and sounds with hieroglyphs, we need to make an `Association`. An Association is a lot like a dictionary or a set of rules.   

```
practiceAssociation = <|"a" -> 1, "b" -> 2, "c" -> 3|>
```
In this example, the letters: "a", "b", "c", are the Keys, and the numbers: 1,2,3 are the Values. Each Key has a Value, and you can look up the Value for a specific Key. In this example, evaluating `practiceAssociation["b"]` gives the number 2.

So let's make an Association for letters (the Keys) to hieroglyphs (the Values). Hieroglyphs represent sounds, so they're not exactly matched to English letters, but they're still fun to experiment with.

--- task ---

Import the images for the hieroglyphs representing the letters A to Z. Drag and drop or copy and paste the images into your notebook.

![a](images/a.png)
![b](images/b.png)
![c](images/c.png)
![d](images/d.png)
![e](images/e.png)
![f](images/f.png)
![g](images/g.png)
![h](images/h.png)
![i](images/i.png)
![j](images/j.png)
![k](images/k.png)
![l](images/l.png)
![m](images/m.png)
![n](images/n.png)
![o](images/o.png)
![p](images/p.png)
![q](images/q.png)
![r](images/r.png)
![s](images/s.png)
![t](images/t.png)
![u](images/u.png)
![v](images/v.png)
![w](images/w.png)
![x](images/x.png)
![y](images/y.png)
![z](images/z.png)

--- /task ---
--- task ---

Build an `Association` with the hieroglyphs. Give the `Association` the variable name `egypt`.

An `Association` starts with `<|` and ends with `|>`. Keys are associated with Values using `<-`, and separated with a `,`. Go back to the `practiceassociation` at the start of this step if you need an example.

![build an association](images/association.png)

--- /task ---
