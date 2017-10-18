# Circles Money System Overview

*A decentralised Universal Basic Income platform based on personal currencies*

**http://joincircles.net**


## Abstract

We propose a new money system called Circles that is based on individualized cryptocurrencies and a social graph of trust between these currencies. This money system will be for the purposes of distributing and maintaining a globally accessible Universal Basic Income. When new users join Circles, a new personal cryptocurrency is created for them on a smart contract-enabled blockchain. This currency is then regularly minted and added to their account, forming the basis of Circles' UBI properties. Users have the ability to trust the personal currencies of other users, which requires them to treat this personal currency as identical to any other Circles currencies that they hold. As the social graph becomes more interconnected, these personal currencies converge on one single global monetary system.

## Introduction

Universal Basic Income is one of the most cross-culturaly appealing political movements of the modern era. It has attracted the support of thinkers from every background including Milton Friedman, Friedrich Hayek, Elon Musk, Martin Luther King Jr, Stephen Hawking, and Noam Chomsky. It is seen as a utopian project that could finally unlock the creative potential of all people, the culmination of centuries-old humanist ideals.

The topic of UBI has exploded in popularity in recent years, as wealth inequality grows and purchasing power falls all across the world. Until now, the conversation has primarily been viewed through the lens of public policy and bureaucratic action. Public support for the idea of UBI has never been higher, but plans for implementation are progressing slowly and without cooperation at the international scale. It seems that UBI systems have received a "too big to implement" label at the highest levels of government, similar to climate change action, making development and rollout unlikely to happen any time soon.

The introduction of global blockchain networks changes the conversation about UBI significantly. Now for the first time in history, it is trivially easy to create financial applications that are universally accessible to anyone on the internet. Starting with Bitcoin and moving on to smart contract platforms like Ethereum, blockchain technology has achieved widespread popularity by routing around the gatekeepers and roadblocks that make innovation so difficult in the legacy financial system. Smart contracts and the blockchain create a very promising environment in which to implement a new UBI system.

Circles proposes to be the blockchain's native UBI money system. It has its own built-in resistance to Sybil attacks (i.e. fake accounts) and anyone can join the network at any time without asking permission from anyone. It has been designed with the expectation that it will be bootstrapped in a completely organic and grassroots fashion, but is extensible to allow any arbitrary governance systems to operate on top of the base protocol. Circles is an entirely new way of looking at the nature of money and what value exchange means in a post-UBI future. 


## Minting Currency

Circles is a money system that is made up of individual currencies. These currencies work together to create an economy that can support Universal Basic Income.

When a new blockchain account joins Circles, the system creates and assigns them a unique currency via a smart contract. This is called a *Personal Currency*, and all personal currencies operate according to a shared set of rules. 

Each personal currency continuously mints new coins and awards them to its associated person. This is the only way that new money is created in Circles and forms the basis of its UBI characteristics. All currencies mint new coins at the same rate, meaning that new money is distributed equally to all members of the system at all times.


```
Alice joins the system, creating AliceCoin
PersonalCoins are all minted at a rate of 1 per minute
Five minutes later Alice has 5 AliceCoin and Bob joins the system, creating BobCoin
Five minutes later Alice has 10 AliceCoin and Bob has 5 BobCoin
```

It’s important to note that new currency units are only awarded to the person associated with each personal currency:

```
Alice joins the system, creating AliceCoin
PersonalCoins are all minted at a rate of 1 per minute
Five minutes later Alice has 5 AliceCoin and Bob joins the system, creating BobCoin
Alice transfers her 5 AliceCoin to Bob
Alice has 0 PersonalCoins and Bob has 5 AliceCoin
Five minutes later Alice has 5 AliceCoin while Bob has 5 AliceCoin and 5 BobCoin
```

### Inflation

In order to disincentivize hoarding and to encourage economic activity, the system will introduce an annual inflation schedule. All personal currencies will issue progressively larger amounts of tokens per second, and new users will always start issuing at a rate that is consistent with all other personal currencies. The inflation schedule is meant to work in much the same way that inflation works in the traditional economy, but the implementation specifics are still an open topic for research.

## Trusting Currency

In order to create useful money, users trust each other’s currencies. Trust is what facilitates exchange in the system. When a user trusts a currency, they tell the system that it is equivalent to any other Circles currencies that they already have. This means that anyone with this trusted currency can automatically trade it for one of your Circles currencies at a one-to-one exchange rate.

```
Bob trusts AliceCoin
Bob has 10 CarolCoin
Dave has 10 AliceCoin
Dave gives 5 AliceCoin to Bob and takes 5 CarolCoin from him
```

Another way of thinking about trust is that it is the user telling the system that they acknowledge specific currencies as “real money.” Since any blockchain account can join the system and start minting currency, a trivial attack is to create multiple accounts and register with each to get multiple basic incomes. This is called a Sybil attack in computer security terms. The existence of trust relationships is how users protect themselves from fake accounts by specifying which ones they know for a fact represent an individual human’s primary account, forming a native Sybil resistance in the system.

Because trust is a way to protect from counterfeit currencies, it is a serious responsibility on the part of the user. Users will have to rely heavily on mutual connections when making direct peer-to-peer trust relationships, and new users with no trust connections will have to get their closest loved ones to be their initial connections. However in order to increase usability, some exceptions to these high requirements are covered in the Validators section below.

### Transitive Exchange

Trusting different currencies creates a useful form of money because of the transitive nature of social networks. Money is useful when it allows complete strangers to efficiently conduct business. When one stranger wants to send money to another in Circles, they automatically search for a transitive chain of trusted currencies between each other. The payer then trades along this chain of trusted currencies, one after the other, until they have one that the recipient accepts.

```
Bob trusts AliceCoin
Alice trusts CarolCoin
Alice has 10 AliceCoin
Carol has 10 CarolCoin
Carol wants to pay Bob 5 PersonalCoins
Carol gives 5 CarolCoin to Alice and takes 5 AliceCoin from her
Carol gives 5 AliceCoin to Bob 
```

![](https://raw.githubusercontent.com/CirclesUBI/docs/master/assets/diagram_1.png)

The transaction can be extended to include multi-hop chains of trust as well: 

```
Bob trusts AliceCoin
Alice trusts CarolCoin
Carol trusts DaveCoin
Alice has 10 AliceCoin
Carol has 10 CarolCoin
Dave has 10 DaveCoin
Dave wants to pay Bob 5 PersonalCoins
Dave gives 5 DaveCoin to Carol and takes 5 CarolCoin from her
Dave gives 5 CarolCoin to Alice and takes 5 AliceCoin from her
Dave gives 5 AliceCoin to Bob
```

![](https://raw.githubusercontent.com/CirclesUBI/docs/master/assets/diagram_3.png)

With this system, the connectedness of the social network serves as a direct measure of users’ ability to transact with each other. A familiar way of thinking about this is the famous six degrees of separation phenomenon that suggests everyone on earth is connected to everyone else by a chain of six people. Circles uses these chains to transact through the system. If a user is well-integrated into the network, with many connections to other well-integrated users, they will find it easier to send and receive personal currency.

### Limits to Trust

Because personal currencies are only able to travel through their networks of trust, the value of a specific personal currency is a measure of how many other accounts trust it. This means that users who are new to the system and don’t have many trusted relationships have a less valuable currency than someone who is well-established in the network. It also means that the currency of new users gets more valuable over time as they create more trust relationships.

Since the system internally enforces a one-to-one exchange rate, and new users’ personal currencies are less valuable than established users personal currencies, a potential problem emerges:

```
25 people trust AliceCoin
Bob is new, so only Alice trusts BobCoin
Bob has 100 BobCoin
Alice has 100 AliceCoin
Bob gives 100 BobCoin to Alice and takes 100 AliceCoin from her
Bob can now spend money with 25 people (and their friends, and friends of friends, etc)
Alice can now only spend money with Bob
```

![](https://raw.githubusercontent.com/CirclesUBI/docs/master/assets/diagram_4.png)

In the example above, Alice needs a way to acknowledge that BobCoin is real money, while limiting her exposure to it while Bob is still new. Circles achieves this with Trust Limits. When you create a trust relationship in Circles, you have the option to include the maximum amount you are willing to accept via automatic exchange per month. With trust limits, Alice is able to help Bob integrate into the system in a more controlled way:

```
25 people trust AliceCoin
Bob is new, so only Alice trusts BobCoin
Alice puts a limit of 10 BobCoin per month on her trust
Bob has 100 BobCoin
Alice has 100 AliceCoin
Bob gives 10 BobCoin to Alice and takes 10 AliceCoin from her
Bob can now spend one tenth of his money with 25 people (and their friends, and friends of friends, etc)
Alice sets aside her 10 BobCoins to spend once Bob has made more trust relationships
Bob gets 10 people to trust BobCoin
Alice raises her trust limit on BobCoin to 100 per month
```

Trust limits reduce the risk of trusting new accounts to the system, making it easier for them to build trust relationships.

### Defending Against Fake Accounts 

As we’ve shown, fake accounts are the primary consideration when designing protections into the system. Since money can be spent indirectly through transitive connections, let’s show how Circles defends against fake accounts that are connected to your friends:

```
Bob trusts AliceCoin
Alice makes a fake account and trusts FakeCoin
Alice has 10 AliceCoin
FakeAlice has 10 FakeCoin
Alice wants to buy something worth 10 PersonalCoins from Bob using FakeCoin
FakeAlice gives 10 FakeCoin to Alice and takes 5 AliceCoin from her
FakeAlice gives 10 AliceCoin to Bob
```

![](https://raw.githubusercontent.com/CirclesUBI/docs/master/assets/diagram_2.png)

This example demonstrates that Bob can only ever receive money that he trusts, and Alice can only ever spend money that other users trust in turn. Even if Alice makes 100 fake accounts and has them all trust each other, she will never be able to spend more than the amount of AliceCoins she has, since that’s the only account that other users will trust. This is why it is crucial that users take direct peer-to-peer trust relationships seriously. 

## Validators

So far the Circles money system is both self-sovereign and resilient to fake accounts, but it is not very user-friendly. New users are given currency that is worthless by default, and they have to take steps to increase its value. This problem is alleviated by the addition of Validators, which allow users to quickly add value to their personal currency.

Validators are blockchain organizations that can create and receive trust relationships just like users can. When a user trusts a validator, they automatically trust the currency of every user that the validator trusts. This means all the users that the validator trusts can transitively use the currency of anyone who trusts the validator. When a validator trusts a new user, they add them as a beneficiary of the trust relationships that the validator has already received. Users achieve this by delegating the work required to validate real accounts to the validator’s administrators. This means that admins have an even higher requirement to ensure that all accounts trusted by the validator are the primary accounts of real people. If a validator’s member set is small, it might mean that the main admin has to personally meet everyone and verify they are a member of the community. If it is large, it might require submitting government issued identification or even biometric data.

```
Bob and Alice make a Validator called TigersFans
Carol signs up for Circles, creating CarolCoins
10 minutes pass and Carol has 10 CarolCoins
Carol asks to be trusted by the Validator and proves that she is a true Tigers Fan. Bob and Alice vote to let her join
Dave trusts the TigerFans Validator
Carol can now spend her CarolCoins with Dave
```

![](https://raw.githubusercontent.com/CirclesUBI/docs/master/assets/diagram_5.png)

Because membership business logic is arbitrary, any type of association can be fronted by a validator. Users might be validated as citizens of a city, tenants of an apartment building, or practitioners of a certain trade. Being validated by popular validators will dramatically increase the reach of a users personal currency. Likewise, users who trust popular validators make it easy for them to receive currency they know will be spendable elsewhere.

## Complementary Currency

Circles is not meant to become the world's dominant currency, cryptographic or otherwise. Rather, it is a complementary currency, working in harmony alongside other stores of value and mediums of exchange. In the future Circles could even serve as a foundational "hard currency" for a more flexible group currency built on top. It is ideal as a hard currency because the supply of specific individual currencies is perfectly predictable and the aggregate system is highly resilient due to its lack of reliance on a centralized identity provider. This hypothetical group currency could function in much the same way that validators work, with arbitrary business logic to determine group membership. The group could then one-way convert the personal currencies of its members into a fungible group currency at a dynamic exchange rate that meets the group's needs over time. This would allow Circles to act as a staging ground for many different experiments in consensus reality (and morality), while still providing individual users the freedom to revert back to personal currencies if any one group becomes corrupted or useless. The possibilities for new political forms are numerous, but the potential for layer 2 systems on top of the base protocol is by far the most speculative aspect of the project and remains a decidedly open question for further research. 

## Conclusion

The Circles Money System was designed to get started creating a UBI economy today. We believe that the combination of resilience and global accessibility afforded by blockchain technology is a key catalyst that makes a Universal Basic Income achieveable within the next generation. Our system's native Sybil-attack resistance and platform for collective governance via Validators make it an ideal focus for grassroots action and community organization, which have been hallmarks of envisioned UBI economies over the years. We are actively researching the economic implications of Circles' various design tradeoffs with the intention of creating a money system that is as useful and stable as possible. Our roadmap is designed to get started with trial applications as soon as possible in order to see how this new form of value exchange behaves in real economic settings. We are very excited about the potential of this project and hope that it can serve as a critical foundation for a new economic paradigm in the decades to come. 
