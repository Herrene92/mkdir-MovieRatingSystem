A nested if checks an additional condition only when the first if is true, while an if-else chooses between two alternative paths at a single decision point.
Using a switch instead of multiple if-else statements makes the code more readable, easier to maintain, and in some cases more efficient when checking one variable against many possible values.
I preferred a `switch` for genre because it’s clearer and scales better than many `else if` comparisons.
The conditional operator simplified a two-way recommendation into a single expression, keeping code compact. 
Short-circuit evaluation is the way Java handle logical AND (&&) and logical OR (||) expressions. It affects it when short curcuit evalutation the right-hand condition in an && or || expression might never run, so any code with side effects inside it will be skipped.
