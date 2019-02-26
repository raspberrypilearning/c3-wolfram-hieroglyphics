## Associating Hieroglyphs with Letters

--- task ---
If you have never used the Wolfram Language before, follow [this guide](https://projects.raspberrypi.org/en/projects/getting-started-with-mathematica) to get started and learn to use the tool. You'll need to look at **Starting Mathematica** and **Programming in Mathematica**.
--- /task ---

In order to represent English letters and sounds with hieroglyphs, we need to make an `Association`. An `Association` is a lot like a dictionary or a set of rules.   

```
practiceAssociation = <|"Mark" -> "English", "Rachel" -> "Science", "Aisha" -> "History", "Omar" -> "Art"|>
```

In this example, the students: Mark, Rachel, Aisha, and Omar, are the `Keys`, and their favourite subjects: English, Science, History and Art, are the `Values`. Each `Key` has a `Value`, and you can look up the `Value` for a specific `Key`.

In this example, evaluating `practiceAssociation["Rachel"]` gives the subject "Science".

You need to start with an `Association` for letters (the `Keys`) to hieroglyphs (the `Values`). Hieroglyphs represent sounds, so they're not exactly matched to English letters, but they're still fun to experiment with. Copying and pasting the images 26 times to create that association might take a little long though, so we've created a starter file you can use.

--- task ---

Download the [starter file](#) and open it in Mathematica.

![An association between hieroglyph images and the latin alphabet](images/association.png)

--- /task ---
