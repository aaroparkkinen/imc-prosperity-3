# Prosperity wiki

### Round 1
#### Algorithm challenge
The first three tradable products are introduced: : Rainforest Resin , Kelp, and Squid Ink. The value of the Rainforest Resin has been stable throughout the history of the archipelago, the value of Kelp has been going up and down over time, and the value of Squid Ink can also swing a bit, but some say there is a pattern to be discovered in its prize progression. All algorithms uploaded in the tutorial round will be processed and generate results instantly, so you can experiment with different programs and strategies.
\
Position limits for the newly introduced products:
\
•	RAINFOREST_RESIN: 50
\
•	KELP: 50
\
•	SQUID_INK: 50
\
Hint
\
Squid Ink can be a very volatile product with price having large swings. Making a two-sided market or carrying position can be risky for such an instrument. However, with large swings comes large reversion. Squid Ink prices show more tendency to revert short term swings in price.
A metric to keep track of the size of deviation/swing from recent average could help in trading profitable positions.
\
#### Manual challenge
\
You get the chance to do a series of trades in some foreign island currencies. The first trade is a conversion of your SeaShells into a foreign currency, the last trade is a conversion from a foreign currency into SeaShells. Everything in between is up to you. Give some thought to what series of trades you would like to do, as there might be an opportunity to walk away with more shells than you arrived with.

### Round 2
Algorithm challenge
In this second round, you’ll find that everybody on the archipelago loves to picnic. Therefore, in addition to the products from round one, two Picnic Baskets are now available as a tradable good.
\
PICNIC_BASKET1 contains three products:
\
Six (6) CROISSANTS
\
Three (3) JAMS
\
One (1) DJEMBES
\
PICNIC_BASKET2 contains just two products:
\
Four (4) CROISSANTS
\
Two (2) JAMS
\
Aside from the Picnic Baskets, you can now also trade the three products individually on the island exchange.
Position limits for the newly introduced products:
\
•	CROISSANTS: 250
\
•	JAMS: 350
\
•	DJEMBES: 60
\
•	PICNIC_BASKET1: 60
\
•	PICNIC_BASKET2: 100
\
#### Manual challenge
\
Some shipping containers with valuables inside washed ashore. You get to choose a maximum of two containers to open and receive the valuable contents from. The first container you open is free of charge, but for the second one you will have to pay some SeaShells. Keep in mind that you are not the only one choosing containers and making a claim on its contents. You will have to split the spoils with all others that choose the same container. So, choose carefully.
Here's a breakdown of how your profit from a container will be computed: Every container has its treasure multiplier (up to 90) and number of inhabitants (up to 10) that will be choosing that particular container. The container’s total treasure is the product of the base treasure (10 000, same for all containers) and the container’s specific treasure multiplier. However, the resulting amount is then divided by the sum of the inhabitants that choose the same container and the percentage of opening this specific container of the total number of times a container has been opened (by all players).
For example, if 5 inhabitants choose a container, and this container was chosen 10% of the total number of times a container has been opened (by all players), the prize you get from that container will be divided by 15. After the division, costs for opening a container apply (if there are any), and profit is what remains.

### Round 3
#### Algorithm challenge
Our inhabitants really like volcanic rock. So much even, that they invented a new tradable good, VOLCANIC ROCK VOUCHERS. The vouchers will give you the right but not obligation to buy VOLCANIC ROCK at a certain price (strike price) at voucher expiry timestamp. These vouchers can be traded as a separate item on the island’s exchange. Of course you will have to pay a premium for these vouchers, but if your strategy is solid as a rock, SeaShells spoils will be waiting for you on the horizon.
There are five Volcanic Rock Vouchers, each with their own strike price and premium.
At beginning of Round 1, all the Vouchers have 7 trading days to expire. By end of Round 5, vouchers will have 2 trading days left to expire.
\
\
Position limits for the newly introduced products:
\
•	VOLCANIC_ROCK: 400
\
VOLCANIC_ROCK_VOUCHER_9500 :
\
•	Position Limit: 200
\
•	Strike Price: 9,500 SeaShells
\
•	Expiration deadline: 7 days (1 round = 1 day) starting from round 1
\
VOLCANIC_ROCK_VOUCHER_9750 :
\
•	Position Limit: 200
\
•	Strike Price: 9,750 SeaShells
\
•	Expiration deadline: 7 days (1 round = 1 day) starting from round 1
\
VOLCANIC_ROCK_VOUCHER_10000 :
\
•	Position Limit: 200
\
•	Strike Price: 10,000 SeaShells
\
•	Expiration deadline: 7 days (1 round = 1 day) starting from round 1
\
VOLCANIC_ROCK_VOUCHER_10250 :
\
•	Position Limit: 200
\
•	Strike Price: 10,250 SeaShells
\
•	Expiration deadline: 7 days (1 round = 1 day) starting from round 1
\
VOLCANIC_ROCK_VOUCHER_10500 :
\
•	Position Limit: 200
\
•	Strike Price: 10,500 SeaShells
\
•	Expiration deadline: 7 days (1 round = 1 day) starting from round 1
\
#### Hint for Algorithmic Challenge
\
Hello everyone, hope you're enjoying the VOLCANIC_ROCK vouchers and a variety of trading strategies these new products introduce. While digging for the rock, Archipelago residents found some ancient mathematics sharing insights into VOLCANIC_ROCK voucher trading. Here's what the message with obscure and advanced mathematics read,
\
Message begins,
I have discovered a strategy which will make ArchiCapital the biggest trading company ever. Here's how my thesis goes,
t: Timestamp St: Voucher Underlying Price at t K: Strike TTE: Remaining Time till expiry at t Vt: Voucher price of strike K at t
Compute,
m_t = log(K/St)/ sqrt(TTE) v_t = BlackScholes ImpliedVol(St, Vt, K, TTE)
for each t, plot v_t vs m_t and fit a parabolic curve to filter random noise.
This fitted v_t(m_t) allows me to evaluate opportunities between different strikes. I also call fitted v_t(m_t=0) the base IV and I have identified interesting patterns in timeseries of base IV.
Message ends.
\
#### Manual challenge
\
A big group of Sea Turtles is visiting our shores, bringing with them an opportunity to acquire some top grade FLIPPERS. You only have two chances to offer a good price. Each one of the Sea Turtles will accept the lowest bid that is over their reserve price.
The distribution of reserve prices is uniform between 160–200 and 250–320, but none of the Sea Turtles will trade between 200 and 250 due to some ancient superstition.
For your second bid, they also take into account the average of the second bids by other traders in the archipelago. They’ll trade with you when your offer is above the average of all second bids. But if you end up under the average, the probability of a deal decreases rapidly.
To simulate this probability, the PNL obtained from trading with a fish for which your second bid is under the average of all second bids will be scaled by a factor p:
$$ p = (\frac{320 – \text{average bid}}{320 – \text{your bid}})^3 $$
You know there’s a constant desire for Flippers on the archipelago. So, at the end of the round, you’ll be able to sell them for 320 SeaShells ****a piece.
Think hard about how you want to set your two bids, place your feet firmly in the sand and brace yourself, because this could get messy.

### Round 4
#### Algorithm challenge
In this fourth round of Prosperity a new luxury product is introduced: MAGNIFICENT MACARONS. MAGNIFICENT MACARONS are a delicacy and their value is dependent on all sorts of observable factors like hours of sun light, sugar prices, shipping costs, in- & export tariffs and suitable storage space. Can you find the right connections to optimize your program?
Position limits for the newly introduced products:
•	MAGNIFICENT_MACARONS: 75
•	Conversion Limit for MAGNIFICENT_MACARONS = 10
\
#### Hint - Algo
\
It was well understood lore in Archipelago that low sunlight index can impact sugar and MACARON production negatively causing prices to rise due to panic among residents. However, ArchiResearchers have identified existence of a CriticalSunlightIndex (CSI).
If sunlightIndex goes below this CSI with an anticipation to remain under this critical level for a long period of time, sugar and MACARON prices can increase by substantial amount with a strong correlation.
When sunlightIndex is above this CSI, Sugar and MACARON prices tend to trade around their respective fair values and demonstrates market supply-demand dynamics.
Can you find this CSI and use it to trade better than ever and make your island prosper? All the best!
\
#### Manual challenge
\
You’re participating in a brand new game show and have the opportunity to open up a maximum of three suitcases with great prizes in them. The whole archipelago is participating, so you’ll have to share the spoils with everyone choosing the same suitcase. Opening one suitcase is free, but for the second and third one you’ll need to pay to get inside.
Here's a breakdown of how your profit from a suitcase will be computed: Every suitcase has its prize multiplier (up to 100) and number of inhabitants (up to 15) that will be choosing that particular suitcase. The suitcase’s total treasure is the product of the base treasure (10 000, same for all suitcases) and the suitcase’s specific treasure multiplier. However, the resulting amount is then divided by the sum of the inhabitants that choose the same suitcase and the percentage of opening this specific suitcase of the total number of times a suitcase has been opened (by all players).
For example, if 5 inhabitants choose a suitcase, and this suitcase was chosen 10% of the total number of times a suitcase has been opened (by all players), the prize you get from that suitcase will be divided by 15. After the division, costs for opening a suitcase apply (if there are any), and profit is what remains.




### Round 5
#### Algorithm challenge
The final round of the challenge is already here! And surprise, no new products are introduced for a change. Dull? Probably not, as you do get another treat. The island exchange now discloses to you who the counterparty is you have traded against. This means that the counter_party property of the OwnTrade object is now populated. Perhaps interesting to see if you can leverage this information to make your algorithm even more profitable?
class OwnTrade:
    def __init__(self, symbol: Symbol, price: int, quantity: int, counter_party: UserId = None) -> None:
        self.symbol = symbol
        self.price: int = price
        self.quantity: int = quantity
        self.counter_party = counter_party
\
#### Manual challenge
You’ve been invited to trade on the exchange of the West Archipelago for one day only. An exclusive event and perfect opportunity to make some big final profits before the champion is crowned. Benny the Bull has granted you access to his most trusted news source: Goldberg. You’ll find all the information you need right there. Be aware that trading these foreign goods comes at a price. The more you trade in one good, the more expensive it will get. This is the final stretch. Make it count!


