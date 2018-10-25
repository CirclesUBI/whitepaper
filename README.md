---
description: Introduction to all things Circles
---

# Circles UBI overview

## What is Circles?

Circles is a Universal Basic Income project that humbly accept that the road to UBI is long, but ambitiously states that we can deal with the challenges on the way.

### Dealing with the challenges of UBI

Circles realizes both the futility of going through slow, bureaucratic institutions and the danger of attempting to use traditional monetary incentive logic, instead it challenges the issue on a more fundamental level. It does this while also realizing there is no single button to push to achieve UBI, instead one has to look at which the next steps are.

{% hint style="info" %}
Circles is a a tool for implementing money issuance as a commons with the seigniorage consistently divided evenly across all users in a basic income like fashion.
{% endhint %}

A strict definition of UBI is difficult to achieve because:

1. It should be universal \(or at least global\)
2. It should be basic, which can be divisive

Respecting the above challenges means aiming for something that does not rely on having to go through the nation state or the market, but instead can be implemented by grass roots movements with minimal resources and spread and/or scale from there. 

Additionally it has to be adaptable to subjective needs, defined by its users, so to this end it retains the two features of being configurable and also necessarily governed by humans as a common pool resource.

That is also why Circles is not _one_ currency but a toolkit for bootstrapping currency. Its ambition is to have all the tools in this kit to address the needs of what UBI could be, but it leaves it up to the individuals and communities that use to to decide on how they should be used.

The assumed operation of Circles is:

1. There is a monetary need which established currency does not fill
2. Individuals that see this need download an app that uses the Circles protocol
3. These individuals can connect to each other and immediately has a tool for exchange
4. The group is able to scale up into a larger organism like a town, which then governs the currency as a commons
5. Further scaling is possible, forking and adaptations of the app and protocol are possible

### F.A.Q.

* Where does the money come from?
  * Where does money normally come from?  Circles makes use of the fact that all money is fiction that attempts to model what humans think value is. Fiat money too, has been off the gold standard for many decades and is now backed by nation states enforcing its value.  In Circles, money is issued without incurring debt on anyone, but it is available for usage only to those who earn trust. Seen this way, Circles is backed by TRUST.
* What about inflation? Won't everything be really expensive if everyone has a lot of money?
  * We don't know this for sure, the correlation between issuance and inflation is not fully understood. If need be, functionality like money sinks or demurrage could be an improvement.
* Does this have to run on a blockchain like Ethereum?
  * Currently, Ethereum is the best available platform for development, but the project is blockchain agnostic and eventually, Circles itself could even be used as a blockchain to build on top of.
* This won't solve war/hunger/racism/sexism/demagoguery!
  * We're sorry about that, but hopefully it can ease a wide swathe of problems.
* This will not work because people are not good-natured!
  * Research shows that people as a whole are in fact very good natured! This project assumes the stance that it is our inability to structure ourselves to express this nature that creates systematic problems, rather than some unavoidable part of human nature.
* Is this project technocratic?
  * We are aware of the currents of technocracy in our sphere and actively seek to disarm it in ourselves, collaborating with a wide range of perspectives and remembering to ask about needs rather than prescribe solutions.
* If the currency is backed by trust, won't that unfairly punish unpopular indviduals?
  * Any individual might be unfairly punished for being unpopular, but in this project we attempt to address concerns like this in a systematic matter, for instance pushing the idea that trust is purely about sybil defense and nothing else. Also by creating neutral, social institutions for this need.
* Can you trade Circles currency to fiat on an exchange?
  * Personal Currencies can not be practically traded for fiat. A larger scale Circles instantiation could have its currency traded for!



## Systematic overview

### Sybil resistance

For UBI to claim to be something close to "Universal", it should at least allow every single individual human to receive income. This is hard for every reason, so let's start somewhere and make the problem managable.

We can decide registration is open for anyone to click a button and create an account which will then have monetary units added to it at an interval. We immediately face a well-known problem, that of sybils. Someone could create two accounts and have double the income! 

Circles uses web of trust as a sybil resistance mechanism through its **Personal Currencies**. 

This web of trust that is Personal Currencies \(PC\), consists of individuals as nodes and their claiming other nodes being non-sybils as directional edges. In English, it is a network of individuals that claim other individuals in the network to be real, to be a single individual and to hold a single account.

This vision fits the purpose of decentralized and grass-roots bootstrapping with minimal resources, meaning Circles can be instantiated without a large, central power, but instead it's enough with a small group of individuals and affordable tools.

The basic rules of PC is first, that you can only receive monetary units created by nodes you trust to not be sybils. This means only the individual that makes the mistake to wrongfully trust a sybil is punished for it, rather than the whole network. Second, saying a node is not sybil means you see their own currency as being equally real to yours and as such you are willing to exchange them freely. The second rule means we can now have Transitive Exchange. Transitive Exchange is programmatically exchanging PC through a chain of trust in order to reach a payment target that does not directly trust you, but only indirectly through the network, allowing for some primitive scaling.

A successful implementation of PC can do that, but it runs into problems at larger scale. A utility or professional organization in a network of PC has to go through many steps to determine if it wants to receive a personal currency. And since it wants to receive many different kinds it will carry a heavier responsibility and take heavier punishment for sybil attacks. Though not impossible by any means, we quickly realize that scaling this anti-fungible money is an unfair and impractical attempt to begin with.

But PC does not exist for the purposes of scaling, it has its purpose stated above. Can't we let PC do its job of grass-roots sybil resistance, while letting other models fulfill purposes such as scaling?

### Scaling

We can attempt a model that allows different logic at different levels of scale, much like in physics where the reality at macro, molecular, atomic and sub-atomic scale work according to different rules, but they build a stable system as a whole.

Personal Currencies then, is Circles reality at an individual scale.

Without breaking the laws of PC, we can add a Community Currency \(CC\) an top. A CC could be issued freely by a currency issuing organ of a community and then be traded for the personal currency of its members. This currency is fungible and it could fulfill other potential monetary utilities from what PC can do. With this, scaling is much easier and the stores can easily trust anyone to pay with their CC without concern.

Some readers will immediately worry about this being a centralized solution, which is correct. Worthy of note, however, is that the community members could have a freedom of choice of a different organ of CC issuance - their individuality as expressed through PC gives a counter-balance to the power of the CC issuer.

So we can say that CC can only exist with PC as a basis, and that it's okay for the rules to function differently at a different scale. That because the concerns at the individual scale can be solved there, we are now free to solve different problems existing at a different scale here.

We could continue this model of scaling, having communities come together too, forming cities, countries, groups of countries, etc.as long as it fits the needs of the organism and is able to support the individuals of the first scale.

