# Code Review and why it matters

## Why Reviewing Code Matters
    So, why does code reviewing matter? After all, we’re all competent here. Surely we can ship code without having someone metaphorically standing over our shoulder, watching everything we do.
    
    In theory, yes. But in practice, there are many reasons why having an established code reviewing process helps. Let’s look at a few of them.

## It limits risks
    This is probably the most important reason of all. Having someone double-checking our work never hurts, and limits the risk of unnoticed mistakes. Even good developers get tunnel vision sometimes.
    
    It’s always good to make sure not to forget anything. For instance, proper keyboard navigation, screen reader accessibility flexibility for internationalization and friendly, non-JavaScript behavior are often forgotten topics in the front-end world, to name but four.

## It dramatically improves code quality
    Let’s make something clear: this is not about standards and code linting (at least not exclusively). It’s about making code more efficient.
    
    In a team where everybody has their own background and strong suits, asking for improvements (because that’s what it’s about) is always a good idea. Someone could suggest a smarter solution, a more appropriate design pattern, a way to reduce complexity or to improve performance.

## It makes everyone better
    By joining forces, everyone can learn and get better. The code submitter is likely to receive feedback on their work, making them aware of possible problems and areas for improvement. The reviewers could well learn new things by reading through the code, and figure out solutions applicable to their own work.

## It helps being familiar with the project
    When a team works on a project, it’s highly unlikely that every developer is working on every part of the application. Sometimes a developer will heavily work on one large part for a while, while another one is working on something else entirely.	
    
    Doing code reviews helps people familiarize themselves with code they haven’t written but might be asked to maintain in the future. It promotes knowledge of the codebase across the team, and is likely to speed up future development.

## How To Do It Properly
    Again, having an established code reviewing process is both extremely useful and important. Every team producing code should have some code review, one way or the other.
    
    That being said, doing meaningful and helpful code reviews is not always as straightforward as it might seem. Worry not,it’s not like it’s going to bite you if it’s done poorly. It simply won’t be useful, and could feel like a waste of time.
    
    Recently at my workplace, we had a retrospective about our code reviewing process. We knew some things were wrong when we realized only 3 out of 12 developers were engaging in code reviews.
    To help us change this, one of our Scrum Masters organized a retrospective to determine where there was room for improvement, and how we could bring it about.

## Planning ahead
    The most recurrent argument to justify the lack of participation in code reviews was that it takes time — time that people can’t or aren’t willing to take.

    I must say I don’t really understand this argument myself, because I picture it like this: if a colleague comes to me directly and asks me to help them with something, I’m not going to say — “Don’t have time, not interested.” I’m going to find time to help. Maybe not right now, maybe in an hour — but I will obviously take time for them. Why? Because
    - this is what being part of a team means
    - if they want my opinion, it’s because they value it one way or another, and therefore it makes only sense to give them.

    To me, a pull request is no different from a coworker asking for help. Saying you don’t have time is perfectly fine from time to time, but by systematically refusing to help, you’re actively pulling yourself out of the team. This behavior is neither friendly nor positive. Take the time to help.
    
    To make it possible for developers to find time, we started taking into account that every developer will spend a bit of time (maybe 30 minutes) reviewing code every day. No more surprise when we end up spending half an hour on a large code review: it’s part of the day.
    
    We also tried to dramatically reduce the amount of code constituting a pull request. We used to have mammoth pull requests — of thousands of changes across dozens of files.

    We try not to do that anymore. By making smaller pull requests, we make them easier to review, the feedback more relevant, and developers more willing to engage in this process. “Ship small and often.”

## Giving context
    The second biggest problem we found was that we usually lacked an understanding of the code’s context, which is needed if you’re going to provide helpful feedback. When missing the context, we usually did no more than a syntax review — which, though useful to some extent, is not enough. You simple become what we call a “human linter”.

    Fortunately, the solution to this problem is relatively simple: add a description to the pull request to explain what the objective is, and how to get there. It doesn’t have to be a wall of text; just a few lines are usually enough. It also helps to add a link to the issue and/or story. Liv Madsen, one of our developers, even adds screenshots — or screencasts when relevant — to illustrate what she’s done, which is amazing.

## Actually asking
    The third problem we pointed out was that we sometimes simply didn’t realize there was something to review. Let’s face it, we’re flooded with tons of emails and notifications every day — so much so that it can be hard to keep track. We’re only human, after all.
    
    Here, again, the solution is pretty simple: actually ask someone for a review. There are many ways to do that, from honking a horn in the office to pinging someone on Slack; to each team their own.

    We created groups on GitHub based on our activity, and when submitting a pull request, we always ping a group. Members of this group will receive a notification and are free to tackle it as soon as they have time. Sometimes, we ping a developer (or several) directly when it’s more specific to someone’s work. That also works.
    From there, pinged people can review the code and leave comments. We try to leave a comment even when there’s nothing specific to report — if only to indicate that the code is ready to be merged.

    Because we had some pull requests blindly merged regardless of given comments, we established a strict “reply or fix everything” policy. When receiving feedback, either you fix it or you reply to explain why you didn’t. In any case, you never leave a comment pending, and you certainly don’t merge your pull request with non-handled comments.

	
## Wrapping Things Up
    Having a regular and efficient code reviewing process is essential to maintain high-quality code standards, grow as a team and share knowledge between developers.

    Asking for a code review is not a mark of weakness. There’s nothing embarrassing about asking for help, and certainly not in the form of a code review. Accept all feedback given to you, and offer constructive (ideally positive) comments to people submitting pull requests.
    
    Find what works for you. Reviewing code should be a large part of the code shipping process, so you should tailor it to your team. Make it the way you want so that it’s helpful and positive for everybody.

_Happy reviewing!_

Source: https://www.sitepoint.com/the-importance-of-code-reviews/
