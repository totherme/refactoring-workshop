# Refactoring Code Smells

This is an interactive, remote-friendly workshop that
teaches refactoring.

The overall flow of the workshop goes like this:

- (10 minutes) Facilitator gives a presentation defining
  refactoring and code smells.
- (15 minutes) Participants individually identify specific
  structural problems in a 70-line Ruby file, posting their
  observations in a chatroom.
- (2 hours) Participants mob-program to fix one problem at a
  time, with the facilitator typing code and promoting
  discussion.
- (30 minutes) The group debriefs with another presentation
  and time for questions and discussion.

## Prerequisites and Limitations

- You'll need a facilitator with strong refactoring skills.
- You'll need some way of video conferencing and collecting
  participant suggestions in a chat log. I've used Zoom for
  this.
- In theory, the workshop should scale up to many
  participants (dozens? hundreds?) but I have not tried it
  on large groups yet.
- I recommend you use IntelliJ or RubyMine as your editor.
  You'll need a paid license, or the program will quit every
  30 minutes. Other editors will work, but you'll have to
  split your screen between tests and code, and the
  automated refactoring support may not be as good.

## Goals

The goal of this workshop is to practice removing code
smells via small, targeted refactorings, using frequent test
runs as a safety rail. The emphasis is on the practice of
refactoring, i.e. **safely and incrementally changing the
design of code without changing its observable behavior**.

A breakdown of the goals:

- **Persuade** participants that...
  - refactoring is a mutually beneficial activity,
    furthering the goals of individual programmers, the
    team, the company, its customers, and the users of the
    product.
  - you don't need to have the perfect design in mind
    before starting to refactor.
  - you *do* need tests before you can refactor safely.
- Give participants time to **practice**...
  - identifying code smells.
  - focusing on one refactoring at a time.
  - incrementally improving a codebase, avoiding big-bang
    rewrites.
  - using the language of code smells to discuss design
    tradeoffs.
  - communicating the motivation for a change in Git commit
    messages.
  - making backwards-compatible changes to an interface
    (e.g. creating a class to hold formerly global methods,
    leaving the existing global methods as middlemen).
- **Demonstrate**...
  - getting fast feedback by running all the tests after
    every change.

## Anti-Goals

This workshop can't do everything—after all, we only have
three hours. Some things we're intentionally *not* going to
cover:

- **Writing tests.** The example code comes with tests,
  which are supposed to be complete. The facilitator should
  communicate to participants that he/she trusts the tests
  and will not need to add more.
- **Refactoring test code.**  If the group ends up
  looking at the test code for any reason, the facilitator
  should mention that the tests are *not exemplary*, but
  that refactoring them is out of scope. Refactoring
  tests presents its own set of pitfalls, and we'd rather
  not address them in this workshop.
- **Fixing bugs.** The participants might find bugs in the
  code, or behaviors they think should be changed. The
  facilitator should remind them that the goal of
  refactoring is to hold behavior constant while changing
  structure. By making the bugfix or feature change later,
  in a separate commit, we'll more clearly communicate our
  intent to programmers who work on this code in the future.

## Definitions

- **Code Smell:** "a surface indication that usually
  corresponds to a deeper problem in the system". Source:
  [martinfowler.com](https://www.martinfowler.com/bliki/CodeSmell.html)
- **Refactoring:** (noun) "a change made to the internal
  structure of software to make it easier to understand and
  cheaper to modify without changing its observable
  behavior". Source:
  [refactoring.com](https://refactoring.com/)
- **Refactoring:** (verb) "to restructure software by
  applying a series of refactorings without changing its
  observable behavior". Source:
  [refactoring.com](https://refactoring.com/)

## Facilitator Guide

### Resources

- Use these slides TODO: LINK
- Handout: glossary of smells/refactorings/patterns (LINK?)

### Before the Workshop

- Practice the presentation. If you like, you can read off
  the speaker notes.
- `git clone` this repository.
- Run `bundle install` to get the dependencies.
- Run `bundle exec rspec spec` to run the tests.
- Open this repository in your IDE.
- TODO: how to configure IntelliJ/RubyMine to run the tests?

### During the Workshop

- Show slides 1-N
   - Anti-goals: we want a picture of where are going before we start
- Last slide contains an image of the IDE with the code
- Ask, "Please write down as many specific structural problems with this code as you can in N minutes, in the Zoom chat. We'll discuss them as a group when everyone is done. Don't worry about translating them into code smells; we'll do that as a group."
- Open the file with the prepared TODO comments in the IDE. Monitor the Zoom chat window. If anyone identifies a problem that isn't already annotated, add it as a comment.
- Remind people when time is almost up. "You have one minute" "finish the thought you're on". If you miss one or two issues in the Zoom chat, that's okay.
- Share your IDE. "I'm going to pick the smallest problem; one that we can fix right now."
- "For the purposes of this exercise, I trust that the tests are complete and will fail if I make a mistake."
- For loop (for each comment; break when there's X minutes left)
   - Match the problem to a code smell. Show the slide for that smell.
   - Refactor the smell away.
   - Show the slide with caveats for that smell. Explain when you wouldn't want to refactor the smell away.
- Show a finished product
- Show the final slides
- Discussion
   - Do you have a favorite pattern not discussed today?
   - How can your team use this? any obstacles?

### After the Workshop

Send participants the following list of resources referenced
by this workshop:

- Martin Fowler's site [Refactoring.com](https://refactoring.com) and its [catalog of refactorings](https://refactoring.com/catalog/)
- The [CodeSmell](http://wiki.c2.com/?CodeSmell) page on [C2Wiki](http://wiki.c2.com)
- [RefactorLowHangingFruit on C2Wiki](http://wiki.c2.com/?RefactorLowHangingFruit)
- [Refactoring.guru](https://refactoring.guru/)
- [_99 Bottles of OOP_](https://www.sandimetz.com/99bottles) by Sandi Metz and Katrina Owen.
