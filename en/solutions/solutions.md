![build an association](images/association.png)

```
newWord = {};
Grid[{
  {Text[Style["Hieroglyphics Keyboard", 24]], SpanFromLeft},
  {Dynamic[Row[newWord]], SpanFromLeft},
  {Row[Table[
     With[{i = i}, Button[i, AppendTo[newWord, egypt[[Key[i]]]]]], {i,
       Keys[egypt]}]], SpanFromLeft}, {Button["Clear", newWord = {}], 
   Button["Delete", newWord = Drop[newWord, -1]], ""}
  
  }, Frame -> True]
```
 
Challenge

``` 
newWord = {};
egyptReverse = AssociationMap[Reverse, egypt];
Grid[{
  {Text[Style["Hieroglyphics Keyboard", 24]], SpanFromLeft},
  {Dynamic[Row[newWord]], SpanFromLeft},
  {Row[Table[
     With[{i = i}, 
      Button[i, AppendTo[newWord, egyptReverse[[Key[i]]]]]], {i, 
      Keys[egyptReverse]}]], 
   SpanFromLeft}, {Button["Clear", newWord = {}], 
   Button["Delete", newWord = Drop[newWord, -1]], ""}
  
  }, Frame -> True]
```