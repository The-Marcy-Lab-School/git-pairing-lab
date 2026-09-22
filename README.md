# Intro to Git and Python Pairing Lab

Get you and your partner comfortable with `git` by writing Python functions
together, one at a time.

- [AI Use on This Assignment](#ai-use-on-this-assignment)
- [Pair Programming](#pair-programming)
- [Instructions](#instructions)
- [Troubleshooting Tips](#troubleshooting-tips)
- [Problems](#problems)
- [Bonus](#bonus)

This lab is about git, not Python. The functions are deliberately small so
that the interesting part is the workflow: how to

- Fork a repository
- `git clone` a remote repository
- `git add` to stage and `git commit` to commit changes
- `git push` committed changes from a local repo to a remote repo
- `git pull` changes from a remote repo to a local repo
- Handle merge conflicts

This workflow does **not** follow best practices, and it will probably create
merge conflicts. That is on purpose, and a great place to learn the
foundations of working together in git.

## AI Use on This Assignment

Use whichever mode matches where you are with this material. Both are fine,
and most people move between them as a concept clicks.

**Tutor mode.** The AI explains, questions, quizzes, and critiques, and you
write every line you submit. For this assignment that means asking it what a
merge conflict actually is, or what `git pull` does that `git clone` does not.
Ask it a hundred questions — that is the whole point. What you do not do is
ask it for the function. Paste this at the start of a chat and it will hold
for the rest of the conversation:

> You are acting as a tutor. Your job is to explain what this coding question
> is asking, clarify confusing wording, and highlight the relevant concepts I
> need to know — but do not provide the full solution or code that directly
> answers the question. Instead, rephrase the problem in simpler terms,
> identify what is being tested, and suggest what steps or thought processes
> might help. Ask me guiding questions to make sure I am thinking critically.
> Do not write the final function, algorithm, or code implementation.

**Implementer mode.** You write a specification first, the AI writes code from
it, and then you verify that code line by line. For this assignment, hold off.
Typing these functions out by hand is what makes the git workflow stick, and
there is very little to specify.

You own every line either way, and you will be asked to explain it.

## Pair Programming

You will work in a pair. Both partners look at the same screen, which creates
two roles:

- The **driver** types.
- The **navigator** watches, checks the code, suggests improvements, and looks
  things up to support the driver.

Both roles matter, and people are often better at one than the other. Switch
often.

## Instructions

Read all of these before you start.

1. You will work in pairs to write Python functions.
2. One partner, **Partner A**, forks this repository. Only one of you forks
   it. Partner B does not fork anything.
3. In the **forked** repository, Partner A adds Partner B as a
   [collaborator](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository),
   so both of you can push to it. Partner A shares the repo URL, and Partner B
   accepts the invitation on GitHub. Check your email if you do not see a
   button.
4. Both partners `git clone` the forked repo into `development/mod-0` using
   SSH.
5. Partner A drives first. Partner A **types out** the first function while
   Partner B reviews and suggests. Then stage, commit, and push to `main`.
6. Check the repo on GitHub to confirm the commit arrived.
7. Now swap. Partner B runs `git pull` to get that commit, **types out** the
   second function, and pushes.
8. Keep swapping for *every* function. Partner A takes the odd numbers,
   Partner B the even ones. Every push means your partner pulls before they
   start.
9. Your commit history should alternate between you, like this:

![A GitHub commit list showing five commits, alternating between two different people](./pairedprogramming.png)

Run your code at any point with:

```sh
python3 main.py
```

## Troubleshooting Tips

### Did you clone the same repository?

Check which remote you are connected to from inside the git directory:

```sh
git remote -v
```

That prints where you `pull` from and `push` to. Both partners should see the
same two URLs, and both should point at **Partner A's fork**, not at the
Marcy original.

### Did you stage, commit, and push?

`git status` tells you. It will say whether you have changes that are not
staged, staged changes that are not committed, and commits that are not
pushed.

### Did you pull your partner's changes?

Run `git pull` before you start typing, every time. Most of the confusion in
this lab comes from skipping it.

### Did you cause a merge conflict?

You will, and that is fine. A conflict means you both changed the same lines,
and git wants you to decide which version wins. Open the file and find the
`<<<<<<<`, `=======` and `>>>>>>>` markers. Delete the parts you do not want,
along with the markers themselves, then stage and commit the result.

## Problems

Write your solutions in `main.py`. Test them as you go, by calling the
function and printing what comes back.

1. Write `five_to_one_hundred` that prints all numbers from 5 to 100.

2. Write `multiples_of_three` that prints every positive number up to 100 that
   is a multiple of 3.
   > Multiples of 3 are `3, 6, 9, 12, 15, ...`

3. Write `multiples_of_three_or_five` that prints every positive number up to
   100 that is a multiple of 3 **or** a multiple of 5.
   > `3, 5, 6, 9, 10, 12, 15, ...`

4. Write `until_num` that takes an integer and prints every number from 1 to
   that number.

   ```python
   until_num(5)    # prints 1 through 5
   until_num(42)   # prints 1 through 42
   ```

5. Write `multiply` that takes two numbers and **returns** their product.

   ```python
   multiply(2, 4)     # 8
   multiply(10, -5)   # -50
   multiply(3, 7.5)   # 22.5
   ```

6. Write `add` that takes two numbers and **returns** their sum. If the two
   values are the same, return **triple** their sum.

   ```python
   add(2, 4)     # 6
   add(5, 5)     # 30, because 5 + 5 = 10 and triple that is 30
   add(6, 6)     # 36
   ```

7. Write `is_negative` that takes a number and **returns** `True` if it is
   negative, `False` if it is positive.

   ```python
   is_negative(3)         # False
   is_negative(-2)        # True
   is_negative(math.pi)   # False
   ```

8. Write `triangle_area` that takes the height and base of a triangle and
   **returns** its area.

   ```python
   triangle_area(5, 7)   # 17.5
   triangle_area(6, 8)   # 24
   ```

9. Write `between_twenty_and_forty` that takes a number and **returns** `True`
   if it is strictly between 20 and 40, `False` otherwise. Note that 20 and 40
   themselves are not.

   ```python
   between_twenty_and_forty(20)   # False
   between_twenty_and_forty(21)   # True
   between_twenty_and_forty(39)   # True
   between_twenty_and_forty(40)   # False
   ```

10. Write `largest` that takes three numbers and **returns** the largest.

    ```python
    largest(4, 6, 8)       # 8
    largest(30, 22, 17)    # 30
    ```

## Bonus

From here, split the questions between you. Instead of alternating pushes, you
will each work on your own **branch** at the same time. Read about the
[git branching and PR process](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/mod-0-command-line-interfaces-git-and-github/4-git-branching)
and try it here. You will each create a branch, open a pull request for your
partner to review and merge, and then deal with merging those branches
together. You got this.

11. Write `print_time` that prints the current time as `HH:MM:SS`. Do not hard
    code the hour, minute, or second. Look up the `datetime` module.

12. Write `is_leap_year` that **returns** whether a year is a leap year in the
    Gregorian calendar.

    ```python
    is_leap_year(2000)   # True
    is_leap_year(1900)   # False
    is_leap_year(2020)   # True
    ```

13. Write `get_extension` that **returns** a filename's extension.

    ```python
    get_extension("hello.txt")   # ".txt"
    get_extension("app.py")      # ".py"
    get_extension("README.md")   # ".md"
    ```

14. Write `absolute_nineteen` that **returns** the absolute difference between
    a given number and 19. If the number is greater than 19, return triple
    that difference.

15. Write `switch_letters` that **returns** a new string with the first and
    last characters swapped.

    ```python
    switch_letters("anne")          # "enna"
    switch_letters("hello world")   # "dello worlh"
    switch_letters("a")             # "a"
    switch_letters("")              # ""
    ```

16. Write `change_string` that **returns** a new string with every character
    replaced by the one after it in the alphabet.

    ```python
    change_string("abc")          # "bcd"
    change_string("helloworld")   # "ifmmpxpsme"
    ```
