#Abstract

#Introduction

#Minting Currency

Circles is a money system that is made up of individual currencies. These currencies work together to create an economy that can support Universal Basic Income.

When a new blockchain account joins Circles, the system creates and assigns them a unique currency. This is called a Personal Currency, and all personal currencies operate according to a shared set of rules. 

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

#Trusting Currency

In order to create useful money, users trust each other’s currencies. Trust is what facilitates exchange in the system. When a user trusts a currency, they tell the system that it is equivalent to any other Circles currencies that they already have. This means that anyone with this trusted currency can automatically trade it for one of your Circles currencies at a one-to-one exchange rate.

```
Bob trusts AliceCoin
Bob has 10 CarolCoin
Dave has 10 AliceCoin
Dave gives 5 AliceCoin to Bob and takes 5 CarolCoin from him
```

Another way of thinking about trust is that it is the user telling the system that they acknowledge specific currencies as “real money.” Since any blockchain account can join the system and start minting currency, a trivial attack is to create multiple accounts and register with each to get multiple basic incomes. The existence of trust relationships is how users protect themselves from fake accounts by specifying which ones they know for a fact represent an individual human’s primary account.

Because trust is a way to protect from counterfeit currencies, it is a serious responsibility on the part of the user. Users will have to rely heavily on mutual connections when making direct peer-to-peer trust relationships, and new users with no trust connections will have to get their closest loved ones to be their initial connections. However in order to increase usability, some exceptions to these high requirements are covered in the Groups & Validators section below.

##Transitive Exchange

Trusting different currencies creates a useful form of money because of the transitive nature of social networks. Money is useful when it allows complete strangers to efficiently conduct their business. When one stranger wants to send money to another in Circles, they search for a transitive chain of trusted currencies between each other. The payer then trades along this chain of trusted currencies, one after the other, until they have one that the recipient accepts.

```
Bob trusts AliceCoin
Alice trusts CarolCoin
Alice has 10 AliceCoin
Carol has 10 CarolCoin
Carol wants to pay Bob 5 PersonalCoins
Carol gives 5 CarolCoin to Alice and takes 5 AliceCoin from her
Carol gives 5 AliceCoin to Bob 
```

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

With this system, the connectedness of the social network serves as a direct measure of users’ ability to transact with each other. A familiar way of thinking about this is the famous six degrees of separation phenomenon that suggests everyone on earth is connected to everyone else by a chain of six people. Circles uses these chains to transact through the system. If a user is well-integrated into the network, with many connections to other well-integrated users, they will find it easier to send and receive personal currency.

##Limits to Trust

Because personal currencies are only able to travel through their networks of trust, the value of a specific personal currency is a measure of how many other accounts trust it. This means that users who are new to the system and don’t have many trusted relationships have a less valuable currency than someone who is well-established in the network. It also means that the currency of new users gets more valuable over time as they create more trust relationships.

Since the system is enforcing a one-to-one exchange rate, and new users’ personal currencies are less valuable than established users personal currencies, a potential problem emerges:

```
25 people trust AliceCoin
Bob is new, so only Alice trusts BobCoin
Bob has 100 BobCoin
Alice has 100 AliceCoin
Bob gives 100 BobCoin to Alice and takes 100 AliceCoin from her
Bob can now spend money with 25 people (and their friends, and friends of friends, etc) and Alice can only spend money with Bob
```

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

##Defending Against Fake Accounts 

As we’ve shown, fake accounts are the primary consideration when designing protections into the system. Since money can be spent indirectly through transitive connections, let’s show how Circles defends against fake accounts that are connected to your friends:

```
Bob trusts AliceCoin
Alice makes a fake account and trusts FakeCoin
Alice has 10 AliceCoin
AliceFake has 10 FakeCoin
Alice wants to buy something worth 5 PersonalCoins from Bob using FakeCoin
AliceFake gives 5 FakeCoin to Alice and takes 5 AliceCoin from her
AliceFake gives 5 AliceCoin to Bob
```

This example demonstrates that Bob can only ever receive money that he trusts, and Alice can only ever spend money that other users trust in turn. Even if Alice makes 100 fake accounts and has them all trust each other, she will never be able to spend more than the amount of AliceCoins she has, since that’s the only account that other users will trust. This is why it is crucial that users take direct peer-to-peer trust relationships seriously. 

#Validators & Groups

So far the Circles money system is both self-sovereign and resilient to fake accounts, but it is not very user-friendly. New users are given currency that is worthless by default, and they have to take steps to increase its value. This problem is alleviated by the addition of Validators and Groups, which allow users to quickly add value to their personal currency.


##Validators

Validators are blockchain organizations that can create and receive trust relationships just like users can. When a user trusts a validator, they automatically trust the currency of every user that the validator trusts. This means all the users that the validator trusts can transitively use the currency of anyone who trusts the validator. When a validator trusts a new user, they add them as a beneficiary of the trust relationships that the validator has already received. Users achieve this by delegating the work required to validate real accounts to the validator’s administrators. This means that admins have an even higher requirement to ensure that all accounts trusted by the validator are the primary accounts of real people. If a validator’s member set is small, it might mean that the main admin has to personally meet everyone and verify they are a member of the community. If it is large, it might require submitting government issued identification or even biometric data.

Because membership business logic is arbitrary, any type of association can be fronted by a validator. Users might be validated as citizens of a city, tenants of an apartment building, or practitioners of a certain trade. Being validated by popular validators will dramatically increase the reach of a users personal currency. Likewise, users who trust popular validators make it easy for them to receive currency they know will be spendable elsewhere.

*Needs Example*


##Groups

In addition to validators, users can join Groups. Groups also add members according to arbitrary business logic, but they add in a new feature in the form of Group Currency. When a user joins a group, their personal currency gains the ability to be one-way converted to a new, fungible currency attached to the group. Anyone can trust this group currency just like they do for personal currencies. This feature makes it easy for businesses and strangers to interact, as a user doesn’t need to think about the currency they are receiving if they trust the group already.

```
Bob and Alice make a Group called TigersFans, which creates a coin called TigerCoin
Bob has 10 BobCoins
Bob converts 5 BobCoins into TigerCoins
Bob has 5 BobCoins and 5 TigerCoins
Carol has 10 CarolCoins
Carol asks to join the Group and proves that she is a true Tigers Fan. Bob and Alice vote to let her join
Carol converts 5 CarolCoins to TigerCoins
Carol has 5 CarolCoins and 5 TigerCoins
Dave trusts TigerCoins
Bob and Carol can spend their TigerCoins with Dave
```

Groups and Validators work in very similar ways. They both need to ensure accounts who want to join are the individual primary accounts of real people. They both make it easy for new users to quickly add value to their currency and they make it easy for strangers to interact. The biggest difference between Groups and Validators is the fact that Groups spread out the cost of someone being removed from the group across all holders of the currency.

```
Bob and Alice make a Group called TigersFans, which creates a coin called TigerCoin
Bob has 10 BobCoins and Alice has 10 AliceCoins
Bob converts 5 BobCoins into TigerCoins and Alice converts 5 AliceCoins into TigerCoins
There are 5 TigerCoins in circulation per group member
Carol asks to join the Group. Bob and Alice vote to let her join without checking if she is a true Tigers fan
Carol converts 5 CarolCoin into TigerCoin
Bob and Alice discover that Carol is not a true Tigers fan and remove her from the group
There are 7.5 TigerCoins in circulation per group member
```

If we assume that the value of a group currency will be based on the aggregate economic output of its members, then all holders of TigerCoins paid a penalty when the currency units per member went up in this example. This same scenario plays out differently when using a validator setup:

```
Bob and Alice make a Validator called TigersFans
Bob has 10 BobCoins and Alice has 10 AliceCoins
Carol asks to be trusted by the TigersFans validator. Bob and Alice vote to trust her without checking if she is a true Tigers fan
Dave trusts the TigersFan validator
Carol spends 5 CarolCoins at Dave’s shop
Bob and Alice discover that Carol is not a true Tigers fan and remove her from the group
Dave now has 5 CarolCoins that he can’t spend with people who trust the TigersFan validator
```

As we can see, there is a distinct tradeoff between Groups and Validators. In the Group case, all holders of the group currency surrender control of the value of their coins to a central administrator in exchange for true fungibility and reduced risk of any one member being removed. In the Validator case, unique currencies make it harder for an economy to be captured by one large currency with a network effect, but users are at a greater risk of being stuck with the currency of a member who the validator no longer trusts. One of the most active areas of Circles research is on the nature of this tradeoff and what options exist to create a useful and fair UBI money system.

#Inflation

#Conclusion