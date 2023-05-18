Hi, I would like to talk about hierachical knowledge representation. Like nested sections in the document or like codebase split into multiple files in multiple folders. I wonder how we chose the "axis" along we make this hierachy. Surely there are many, but we chose particular one. And also how this choice imapcts the way we later process the data.

It appears that the choice of the hierarchy should be optimalized for "ease of use". This is a very universal criterion, and all other aspects are a special cases of it. To be more precise, we should care about preserving locality. That is interdependant parts should be on a common branch. In other words stuff accesses often together should have as much of its path common. Or if we want to consult something with a document all relevant parts should be close together. This is the optimal scenario.

But some times the way we use information changes. For example producer of a document can structure it along different axis that is needed later for the consumer.

Ok, i see. This is like indexing a database, but we can have only single index. The question is how can we optimize the choice of the main and only index. I want to deepen that understanding.

But maybe the index choice is not so important. We can choose whatewer we like and if a need for a different index emerge we can reindex.

I see how we can reindex. Lets forget about planning optimal structure when we can relatively easily reindex the data. So to reindex we read all chunks (like sections) and for each chunks we output pairs of (target path, data). This way we produced a new locality. Then we should read data collected for each new path and unify it into a single piece of information. Of course this is crude algorithm but for now it is enough.

But another problem is how we get to know how should we structure our information for a given task. For example we have a business document describing functions of intended system and we would like to change the axis to produce a new document for developers to guide them. It should be sliced along different axis. How to determine it?

Ok, lets suppose it is "more art that science" (which I don't fully believe). How do we even specify the slice axis? How do I describe how the target document should be strucutred?

One possibility of specyfing the structure is to give the exact structure. Information should be mapped into this new structure. Maybe the new structure can be incomplete on lower levels as it can be refined later, as soon as we map some information to the lower level. When a node becomes to crowded we can split it into a subtree and we have a freedom to choose the axis of this split.
