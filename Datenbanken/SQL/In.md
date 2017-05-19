# In

Der In-Operator wird für Gleichheitsabfragen verwendet, wobei mehrere Werte zur Verfügung stehen können.

Alternativ zur direkten Angabe kann dies auch in Form einer Unterabfrage geschehen.

```SQL
SELECT * FROM people WHERE born IN(1990, 1991, 1992);

SELECT * FROM people WHERE born IN(SELECT year FROM superbowl WHERE winner="New England Patriots");
```
