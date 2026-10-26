<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name:MADHANRAJ P</h3>
<h3>Register Number:212223220052</h3>
<h3>Date: 26-10-2026

<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

<h2>Program:</h2>

```
import random
import string

answer = input("Enter the String: ")
s = "".join(random.choices(string.printable, k=len(answer)))

while s != answer:
    score = sum(abs(ord(s[i]) - ord(answer[i])) for i in range(len(answer)))
    print("Solution:", s, "Score:", score)

    i = random.randint(0, len(answer)-1)
    new = s[:i] + random.choice(string.printable) + s[i+1:]

    if abs(ord(new[i]) - ord(answer[i])) < abs(ord(s[i]) - ord(answer[i])):
        s = new

print("Solution:", s, "Score: 0")
print("Target String Found!")
```
<h2>Output:</h2>
<img width="893" height="462" alt="Screenshot 2026-10-26 090823" src="https://github.com/user-attachments/assets/ebff15a4-49ae-4c04-a863-4609e43dc593" />

<hr>
<h3>Result:</h3>
<hr>
<p>Thus,Hill climbing experiment was done successfully.</p>
