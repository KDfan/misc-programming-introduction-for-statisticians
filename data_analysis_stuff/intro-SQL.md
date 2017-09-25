If you're lucky, a lot of your data will be found in SQL databases. SQL is the language you will be using to tell these databases what you want, getting it into the form you want (e.g a R dataframe or a SAS table) is another matter altogether and won't be covered here. 

Only context you need to know: Every software that interprets your SQL code will mostly have special features specific to that software, for example Microsoft doesn't only provide you with 'SQL' but also other features, together they're referred to as T-SQL. Every vendor will try to provide you with the bare minimum features, collectively known as ANSI SQL. Thus when writing code it is reconmended you use as much ANSI SQL as possible so that you can plug and play your scripts in other environments.

Back to SQL itself, SQL is different from other programming languages in that instead of telling the computer what to do, you describe what you want.

E.g:
```
Select top 10 id from some_table where status = 'ACTIVE';
```

Technically described as a declarative language (see here: https://stackoverflow.com/questions/10925689/functional-programming-vs-declarative-programming-vs-imperative-programming).

I won't go over SQL in detail, I just want to go over the most important thing that a novice mathematician would need to know, the order of operation in a select statement. In a normal SQL block of code you will generally see the following keywords (note select is usually first but I'll expand on that later):

1. FROM : where data is coming from (could be another question, google subqeury, correlated sub qeuries and common table expressions)
2. WHERE : filter the from statement
3. GROUP BY : can't explain succintly, I'll come back to this one day, ideally I need a paragraph
4. HAVING : like the where statement, but acts as a filter for groups
5. SELECT : which columns to extract, you can specify basic columns, note that anything here must be present or derivable from the FROM statement
6. ORDER BY : how to arrange the rows

Note the order I placed these in, in any block of SQL code, regardless of the order you wrote the code, the SQL software will execute statements in that block in this order. 

In T-SQL(SQL server) these will typically execute before the control flow contructs, by this I mean IF; THEN; etc etc, use GO statements where necessary. 

And there you have it, you know probably 80-90% of all you'll ever need for SQL, you should be able to debug most things now if you have a vague idea of what to expect. Leave architecture stuff like deciding what to index and such to the professionals, we're only interested in data.

