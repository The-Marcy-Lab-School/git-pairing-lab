# Intro to Git and Python Pairing Lab

Get you and your partner comfortable with `git` by writing a story using the Python `print()` function
together, one sentence at a time.

- [AI Use on This Assignment](#ai-use-on-this-assignment)
- [Requirements](#requirements)
- [Pair Programming](#pair-programming)
- [Instructions](#instructions)
- [Troubleshooting Tips](#troubleshooting-tips)
- [Problems](#problems)
- [Bonus](#bonus)

This lab is about git, not Python. The interesting part is the workflow: how to

- Fork a repository
- `git clone` a remote repository
- `git add` to stage and `git commit` to commit changes
- `git push` committed changes from a local repo to a remote repo
- `git pull` changes from a remote repo to a local repo
- Handle merge conflicts

While doing this workflow, you will probably create
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

## Requirements

You will work in pairs to write Python `print()` statements to tell a story! 

You can tell any story that you want (keep it appropriate for school/the workplace) but **your story must have at least 10 separate `print()` statements.**

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

2. One partner, **Partner A**, forks this repository. Only one of you forks
   it. Partner B does not fork anything.
3. In the **forked** repository, Partner A adds Partner B as a
   [collaborator](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository),
   so both of you can push to it. Partner A shares the repo URL, and Partner B
   accepts the invitation on GitHub. Check your email if you do not see a
   button.
4. Both partners `git clone` the forked repo into `development/mod-0` using
   SSH.
5. Partner A drives first. Partner A **types out** the first `print()` statement while
   Partner B reviews and suggests. Then stage, commit, and push to `main`.
6. Check the repo on GitHub to confirm the commit arrived.
7. Now swap. Partner B runs `git pull` to get that commit, **types out** the
   second function, and pushes.
8. Keep swapping for *every* `print()` statement. Every push means your partner pulls before they
   start.
9. Your commit history should alternate between you

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

## Bonus

From here, split the story. Instead of alternating pushes, you
will each work on your own **branch** at the same time. Read about the
[git branching and PR process](https://marcylabschool.gitbook.io/swe/computational-thinking-and-responsible-use-of-ai/mod-0-command-line-interfaces-git-and-github/4-git-branching)
and try it here. You will each create a branch, open a pull request for your
partner to review and merge, and then deal with merging those branches
together. You got this.
