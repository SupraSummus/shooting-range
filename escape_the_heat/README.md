Escape the heat
===============

Today, on a train, I saw the WWF commercial: "We are an endagered species. One degree centigrade more and it's over. What can you do?" (Check it out at <https://cop.wwf.pl/en/>. I don't know if this is 100% legit.) Recently I've heard about report on climate change so that added up to "care about the world" mode and got me thinking.

So what can we do about increasing temperatures? Here is my try on how to solve the problem. (And I'm totaly not educated in that matter.)

Environmental cost
------------------

First of all it's not about global, average temperatures. It's about the impact of human activity on the environment. In other words the goal is to make impact on envronment as small as possible - to use very little external resources - to minimize the environmental cost of everything we do... Without ceasing to exist and still having fun, of course. I assume that once left alone, the environment will come back to equilibrium by itself and that means that temperatures will be "normal" again.

Environmental cost is tricky. Does using incondesent lightbulbs have large env. cost? Does mining coal have large env. cost? (Let's say mining = taking pile of stone from -500m, crushing it and putting it at level 0m.) Is the environmental cost of making a 1kg piece of bread larger than making 0.2kg of cane sugar? Is it better to travel by car or on horseback, by the env. cost means? Yep, I didn't define the *environmental cost* formally enough, so it's hard to tell the answers.

For now I'll leave it here.

Role of an individual
---------------------

We all want to matter, to decide, to have a vote. What is the vote in the case of rescuing the environment? How one can change the way mankind's economy uses resources? Simple - by having a choice on what she buys. An individual can support selected organizations (and therefore it's style of using resources and environmnet) by spending money to them and not to others. Fortunatelly, we often have this possibility.

To make a choice consumer has to be informed about the results of each possible action. So, in the case of preserving the enviornmet, each product has to be labeled with it's environmental cost. Then the customer can decide consciously on what is best for our homeland Earth.

For this scheme to work, the env. cost has to be defined strictly and has to be a continous value. Different suppliers has to use the same definition of env. cost. Probably it's computation should be supervised by some independent organisations to avoid frauds. Continous value (positive floating point number) is required, because env. cost is lienar in respect to amount. If one car has env. cost of `X`, then two cars (same as the first one) has env. cost of `2*X`.

Computing the env. cost
-----------------------

Okay, we need very strict definition of env. cost that yields a number. I'd say that:

> Environmetal cost of doing `T` is equal to the growth of entropy during doing `T`.

Entropy has the required property that doing nothing is the optimal thing to do (entropy is 0, env. cost is 0) and nothing can be better (smaller than 0). It also reflects the intuition that reversible actions are not so bad. The more an action is reversible the better. Fully reversible actions (possible only in theory) have env. cost of 0.

Requirement to compute entropy increase for all production processes for all organisations is a pain. We need simplification to make the idea more suitable for everyday life.
