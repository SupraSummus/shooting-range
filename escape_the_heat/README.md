Escape the heat
===============

Today, on a train, I saw the WWF commercial: "We are an endangered species. One degree centigrade more and it's over. What can you do?" (Check it out at <https://cop.wwf.pl/en/>. I don't know if this is 100% legit.) Recently I've heard about report on climate change so that added up to "care about the world" mode and got me thinking.

So what can we do about increasing temperatures? Here is my try on how to solve the problem. (And I'm totally not educated in that matter.)

Environmental cost
------------------

First of all it's not about global, average temperatures. It's about the impact of human activity on the environment. In other words the goal is to make impact on environment as small as possible - to use very little external resources - to minimize the environmental cost of everything we do... Without ceasing to exist and still having fun, of course. I assume that once left alone, the environment will come back to equilibrium by itself and that means that temperatures will be "normal" again.

Environmental cost is tricky. Does using incandescent light bulbs have large env. cost? Does mining coal have large env. cost? (Let's say mining = taking pile of stone from -500m, crushing it and putting it at level 0m.) Is the environmental cost of making a 1kg piece of bread larger than making 0.2kg of cane sugar? Is it better to travel by car or on horseback, by the env. cost means? Yep, I didn't define the *environmental cost* formally enough, so it's hard to tell the answers.

For now I'll leave it here.

Role of an individual
---------------------

We all want to matter, to decide, to have a vote. What is the vote in the case of rescuing the environment? How one can change the way mankind's economy uses resources? Simple - by having a choice on what she buys. An individual can support selected organizations (and therefore it's style of using resources and environment) by spending money to them and not to others. Fortunately, we often have this possibility.

To make a choice consumer has to be informed about the results of each possible action. So, in the case of preserving the environment, each product has to be labeled with it's environmental cost. Then the customer can decide consciously on what is best for our homeland Earth.

For this scheme to work, the env. cost has to be defined strictly and has to be a continuous value. Different suppliers has to use the same definition of env. cost. Probably it's computation should be supervised by some independent organizations to avoid frauds. Continuous value (positive floating point number) is required, because env. cost is linear in respect to amount. If one car has env. cost of `X`, then two cars (same as the first one) has env. cost of `2*X`.

Computing the env. cost
-----------------------

Okay, we need very strict definition of env. cost that yields a number. I'd say that:

> Environmental cost of doing `T` is equal to the growth of entropy during doing `T`.

Entropy has the required property that doing nothing is the optimal thing to do (entropy is 0, env. cost is 0) and nothing can be better (smaller than 0). It also reflects the intuition that reversible actions are not so bad. The more an action is reversible the better. Fully reversible actions (possible only in theory) have env. cost of 0.

### Env. cost at the source

Requirement to compute entropy increase for all production processes for all organizations is a pain. We need simplification to make the idea more suitable for everyday life. Let's compute entropy only at the source, that is for the process of extracting resources from environment assuming that all resources are used immediately in a way which increases entropy the most.

For example let's consider mining coal. The sole act of mining is very neutral, because it's reversible. You can take mined coal and put it back into the mine shafts quite easily. The only irreversible aspect is that you burned fuel or used electricity (dissipated it as heat) to power your mining machines (and the un-mining machines). But with assumption that coal is used immediately with the worst effect possible, the entropy of mining (extracting from environment) coal is greatly increased. The worst way to use coal (in terms of entropy) is to burn it in Earth's atmosphere (it's arbitrary), at it's maximum burning temperature (each fuel mixture has max burning temperature impossible to surpass) and then dissipate the heat into perfectly cool environment (let's say 0K - it's arbitrary). Of course, you can do much worse burning coal in pure oxygen atmosphere or in pure fluorine atmosphere, but these resources are not available from our environment directly. In fact, in our model, mining coal is strictly connected to using Earth's atmosphere, because we assume reacting them with each other.

Another example: extracting wood. Wood can be used to make furniture with quite small entropy increase, but worst option is, again, to burn it all. And we assume it is consumed like this. This way we are preserved from frauds like: someone's cutting trees and selling wood as a material for furniture, but the buyer actually uses it by burning. Because we aren't inspecting all processes in all organizations we cannot detect this abuse. So, the safe way is to consider worst scenario no one can beat. Actually, have you ever wondered where all the wood that we use ends, even if it's incorporated in furniture or buildings? It's all eventually burned, sometimes by fire, sometimes by bacteria at the garbage pile.

Interesting thing that mining iron ore has environmental cost of 0 (or nearly 0). This is because you really cannot do much with just iron ore, Earth's atmosphere and water. You need coal (or other reducing agent) for that, which has it's own env. cost. Because of this recycling iron is better than making new iron from ore - you don't need reducing agent for that, just heat.

What about agriculture? What is the environmental cost of growing wheat? Well, it's equal to the cost of preventing native plants from using the sunlight in that area. So, it's equal to dissipating sunlight power reaching the area adjusted for native plant's photosynthesis efficiency in given area. (Or something like this. I didn't analyzed it deeply, but I'm sure it can be done.) So, the cost of using the dessert area is small - photosynthesis efficiency there is small. This applies also to solar power plants and using space for anything - factories, roads, etc. It all boils down to the statement that area occupied by native ecosystem is also a resource and we should minimize the use of it.

Let's get back to one major advantage of computing env. cost at the source: In developed countries all environment resources are centrally controlled by the government (I believe). Each organization that wants to utilize them is supervised by the country. This makes computing the cost relatively easy - for each resource utilization spot (mine, forest, agricultural area) specific env. cost (env. cost per resource amount) has to be computed (each coal mine has different type of coal, which has different specific env. cost) and then multiplied by amount utilized (and reported to the country) by organization on that spot.

### Propagating env. cost through production chain

Once we have environmental cost of base resources we can propagate them up to the products made from those resources, and then to the products made from those products and so on. To efficiently do this we need to assume each organization is a black box and flow of environmental cost is connected to the flow of money. Then computing environmental cost of anything can be done using financial transaction data (and I believe every developed country has record of it for tax computing purposes).

In other words we compute env. cost per currency unit for every organization.

So, for example coal mine "produces" coal, which have env. cost of `E`. The coal is then sold to power plant, and the cost of the coal is, let's say, 40% of total mine's income. Thus the electricity produced by the power plant has env. cost of `0.4*E`. Power plant sells electricity to 1000 customers at equal prices and in equal quantities. One of the customers is a server space provider, which uses the electricity for powering servers. Let's say it has income of `1000$` (in the considered time range), so buying server for `1$` has env. cost of `(0.4*E) / 1000 / 1000` (it is only the "electricity related" cost).

This approach has the downside of unifying all products of an organization, but it should depict the fact that some organizations care more about environment than others. Of course you cannot treat environmental cost of organization products absolutely, because it is relative metric. Products of heavy industry will always be more costly than services (probably). Env. cost is suitable for comparing cheese A to cheese B on grocery store shelf, but not comparing in-ox rods to psychotherapist visit.

Another problem is how to compute cycles - for example coal mine produces coal, which is converted to electricity, and some part of the electricity is then used by coal mine. So we have a system of equations:

    coal env cost = electricity env cost * electricity consumed by mine ratio + source env cost of coal mining
    electricity env cost = coal env cost * coal consumed by power plant ratio

It gets more and more complicated as the cycles gets more complicated, and I suppose they are in modern world. Everything depends on everything. Possible solutions include analytic or iterative solving.

One more problem: time resolution of env. cost computation. Every transaction changes env. cost computation slightly, and it's possible that env. cost have an effect on transactions (because people and organizations care about environment and choose products with small env. cost - ideally). This results in another loop, which this time cannot be solved strictly. We can introduce intervals in which env. cost is computed. Lets say it's computed once per year to adjust to natural energy/entropy cycle. (It'll be hard to compute cost of using ground area with smaller time resolution.) This potentially leads to frauds, because it takes one year to propagate bad news to the customers. So organization has one year to do bad things to the environment before it gets punished by customers.

### Edge cases

Some resources has difficult to define env. cost. Few examples:
 * water power plant and wind power plant - it's arguable if they are consuming environment resources. They are utilizing them for sure, but not using them up.
 * nuclear power plant - it definitely consumes environment resources (heavy elements fuel and cooling agent - they usually heat up water in nearby lake or sea) and they definitely increase entropy during that. It's hard to compute theoretic env. cost of fuel as, unlike chemical fuels, it can reach very high temperatures. Even if possible to compute, I suppose the env. cost of nuclear fuel is extraordinary large, and cannot be fully utilized (conversion to electricity has relatively low efficiency) thus electricity produced by nuke power plant has too high env. cost. Second, it's arguable if nuclear fuel is usable naturally in the environment (deuterium in seawater), so taking it away is not really exploitation - thus env. cost should be low.

Using env. cost for effect
--------------------------

As I proposed earlier, one way is to label products with their env. cost. Customers can then choose consciously. Labeling may even be voluntary - if customers care, they will choose products that are labeled, and this puts pressure on organizations to label their products.

Env. cost per income can be published in central index. I believe it's not revealing any organizations secrets. If the values can be reverse-engineered to reveal network of money flow, then random noise can be introduced to prevent that.

Env. cost can be kept secret, and used only as a guideline for central management. For example government can direct organizations of high env. cost to change their operations. This is risky, as it's crucial to compare company env. cost with what the company is really doing - for example mines have large env. cost per income, but this is not necessarily bad. It's just specific for what they do. On the other hand some mines can have env. cost too large and can be falsely justified for that.

Env. cost can be used to compute "level of being green" not only for companies, but also for governments, cities, etc. It can be used to compare different investment scenarios. Individuals can can compute their env. cost - for example per month - and/or set their goals for reducing (or increasing - if the are evil) their total env. cost.
