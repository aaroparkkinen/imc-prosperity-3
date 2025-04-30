# imc-prosperity-3


Trader Joe’s report – IMC Prosperity 3 
Conor Grant, Aaro Parkkinen, Hamish Poole

IMC Prosperity 3 was a global 15-day algorithmic trading competition held from April 7th to 22nd, 2025. Spanning five distinct rounds – each lasting three days – the competition involved intensive algorithmic trading challenges manual trading tasks. The competition required strong coding and mathematical ability, intuition, and 
Each round comprised two parts: an algorithmic challenge and a manual trading problem. The algorithmic component was cumulative, with each round introducing new products and market information, increasing both in complexity but also trading opportunities to increase potential profits. After each round, submitted algorithms were evaluated in a simulated marketplace. We finished globally in the top 4% of teams – 462nd out of the 12,621 total participating teams.

	462nd Globally
	4th in Ireland
	736th in algorithmic trading
	318th in manual trading

Team introduction
Conor and Aaro are final-year Financial Mathematics students from University College Dublin. Our team also included Hamish, a software engineer from Australia, whom we connected with through the IMC Prosperity Discord. This report is written from the perspective of Conor and Aaro (we), also acknowledging the strong participation and valuable efforts from our teammate Hamish. 

Why we took part in IMC Prosperity 3
We are two students with excellent academic performance and a strong mathematical ability. Both of us are passionate about investments and trading, actively follow the financial markets and continuously try to learn a more about investing – both of us have been actively investing our savings since turning 18. Furthermore, Aaro has completed an internship in trading, which provided us with a solid technical foundation going into the competition. We were keen on expanding our computational expertise, challenge ourselves, and prove our capabilities leading us to enter the competition.

Thoughts and learning outcomes
Start of this challenge, we had strong mathematical foundation and intermediate-level coding knowledge. In Python, we were comfortable creating functions, loops, conditionals and using arrays for example, to price options, conduct Monte Carlo simulations, and implement numerical methods such as Newton-Raphson. We also had basic knowledge about data visualization, analysis using libraries like pandas and matplotlib. 
However, the challenge forced us to acquire many new skills quickly. IMC Prosperity used object-oriented programming (OOP) in Python, which we were not familiar with. Over the two weeks, we learned a massive amount of new coding concepts, key techniques to write new code and ways to de-bug it. We began testing the efficiency of our code and added visualizers and back-testing tool into our process to create and evaluate new strategies. 
We also adopted GitHub as our primary collaboration tool, which was crucial for maintaining clear communication across time zones and keeping track of each team member’s progress and findings. By the end of the competition, our code had become well-organized, modular, and easy to read and modify. From round three onwards, we implemented back-testing and visualisation to analyse our trading accelerating our process from data analysis to writing code and determining its performance.

Algorithmic Rounds
The algorithmic trading challenge ran continuously over the 15-day competition, with each round introducing new products or market information. This progressively increased the opportunities for profit while adding to the complexity and total workload. All the algorithms centred around object-oriented programming requiring us to familiarise a new way of coding and its rationale. In the first round, we spent significant time trying to understand the provided codebase just to even get a single trade to execute. Recruiting Hamish through Discord helped ease the initial coding burden, allowing us to focus more and developing trading strategies and analysing given data.
We quickly learned that analysing historical data—extracting and visualizing key metrics—was extremely time-consuming. We had multiple sessions of analysis and coming up with ideas only to apply these into a code that turned out the be dead-end. Being efficient with back-testing turned out to be one of the core competencies in this challenge require to succeed in the given timeframe.
Overall, we learned a tremendous amount about coding and adopted several good habits that will serve us well in future projects. Sharing and organising our work efficiently became essential. By round 3, we were all working on the same codebase, improving our collaboration and made it easier to share our findings and fails through GitHub. 
Trading strategies
Rainforest Resin: This product was an actively traded commodity worth 10,000 SeaShells, typically traded around 0.1 % of its true price. We implemented a market-making strategy to sell above and buy below the 10,000 mark, profiting from the bid-ask spread.
Kelp: For this product, we applied a similar market-making strategy. Since this product didn’t have a ‘true price’, the market making was adjusting continuously… We were experimenting with different momentum-based strategies and Bollinger bands, however, the product too relatively stable, and we unable to find a consistently profitable strategy. 
Squid Ink: This product was the most time-consuming throughout this challenge. Initially, we pursued a momentum-based strategy, to capture profits from its large price swings. After those proved unstable, our focus drifted towards short-to-medium term mean reversion approach. Despite extensive modelling trying to quantify the key metrics to make this strategy work and we never really got a functional stable strategy.
Jams, Djembes and Croissants: These products had low Average Ture Range (ATR) values, moving very little daily. We utilized floor/ceiling prices to try to trade relative price ranges, which proved to outperform momentum and market making strategies, and eventually developed slightly profitable, stable strategies to these products.
Picnic Baskets: The two Picnic Baskets functioned as ETFs consisting of a mix of the three previously mentioned products: Jams, Djembes and Croissants. Our strategies for both baskets focused on identifying price discrepancies between baskets and sum of their components. We used principles of arbitrage to buy when baskets were undervalued and sell overvalued. These strategies worked reliably and created a constant income source for us.
Volcanic Rock: Volcanic Rock was a highly volatile asset with large moves and ability to trade in large volume, offering massive trading potential. We initially implemented a momentum-based strategy, which became one of our best performing strategies. However, we then realised our mistake of overfitting and the strategy turned out to be quite unstable as market conditions changed. Trading Volcanic Rock thought us some of the most valuable lessons of the competition: the importance of using multiple back-testing methods, avoid overfitting, managing risk on volatile environments and remain adaptive to changing market conditions.
Vouchers: The Vouchers functioned European-styled call options Volcanic Rock with different strike prices. We calculated time to expiry and realised volatility using recent price history and applied Black-Scholes model to determine the fair value of each option. Our approach was arbitrage-based trying to buy undervalued and sell overvalued options, which worked quite well on options out-of-the-money where the moneyness of options were at a reasonable level, and mispricing occurred more frequently. By round 5, due to time constraints, we were unable to add a tracker for the price of Volcanic Rock, to determine which options to trade and which were deep in the money making our algorithm non-functional. As a result, we removed the 9500 and 9750 strike options from our active strategy for simplicity and reduce risk.

Skills learned
	Object-Oriented Programming (OOP) in Python
	GitHub collaboration and version control
	Use of visualizers and back-testers

Manual Rounds
The manual rounds consisted of solving trading challenges based on round-specific information. The questions consisted of optimisation, game theory, manipulating probability distributions and interpreting how news and information could affect asset prices. Every round tested our intuition, strategic decision-making and application of computational and mathematical tools to evaluate different scenarios.
Round 1 – Currency Arbitrage
	Snowballs	Pizza	Silicon Nuggets	SeaShells
Snowballs	1	1.45	0.52	0.72
Pizza	0.7	1	0.31	0.48
Silicon Nuggets	1.95	3.1	1	1.49
SeaShells	1.34	1.98	0.64	1

We were given 40,000 SeaShells, the base currency of the challenge and the opportunity to trade three foreign currencies up to 5 total trades. To solve this, we simulated all possible trade sequencies and picked the most profitable one: SeaShells -> Snowballs -> Silicon Nuggets -> Pizza -> Snowballs -> SeaShells. This was a simple currency arbitrage problem.
Rounds 2 – Containers
This round involved picking one or two containers out of ten options. Each container had a base reward of 10,000 SeaShells, multiplied by its specific multiplier and number of base inhabitants picking that container. The reward of each container is split between the base inhabitants and percentage of teams selecting that container. 
We performed a sensitivity analysis for the containers, looking at the possible scenarios and other teams approaches to this problem. Our hypothesis was that most teams would be risk-averse favouring containers with large multipliers that were less sensitive to overallocation. This drifted us to look at the lower multiplier containers. The 10x container being the least sensitive seemed too risky due to it being technically the worst pick out of all the containers, possibly drawing more attention to it. Hence, we looked evenly containers 20, 31 and 37, which we believed would perform the best. 
 
Ultimately, we decided to choose 31, which unfortunately ended up being the worst out of these three, returning around an average payoff of 34,000 SeaShells from this challenge. We chose not to select a second container due to the high additional fee (50,000), expecting that at most two containers would yield this profit making this too risky.

Round 3 – Auction
This round, we had the chance to trade flippers with Sea Turtles by submitting two bids. The problem combined game theory and optimisation. The Sea Turtles would accept the our lowest bid exceeding their reserve price, which was uniformly distributed within two ranges: 160-200 and 250-320. After the auction, the flippers could be sold again at a fixed price of 320. The first pick was purely optimised by finding the highest expected return, turning out to be 200. For the second bid, the average of every team’s second bid affected the overall decision, profits made below the average were reduced by a factor:
 
Being below the average bid turned out to be significantly more costly than bidding slightly above it. From purely optimising the second bid, 285 gave the highest return and we ultimately submitted 297 as our second pick. Most teams were bidding very close to the ‘optimal’ solution, showing low risk-aversion and average bid turned out to be 287, which resulted in a slight loss for us compared to the overall field.

Round 4 – Container 2.0
This round was an extension of round 2, but with 20 containers. This time there was the option to choose one container for free, second one for 50,000 and third for 100,000 Seashells. The increased number of options changed the dynamics, reducing the likelihood of any single container would receive over 8-10% of the total picks. All participants got reminded of how well the low multiplier containers did in round 2 creating a shift in mindset within participants. Our sensitivity analysis clearly indicated us toward higher-multiplier containers. Our rationale was that every team would also do the analysis and go for safe profits. This turned out to be the wrong hypothesis and the big profits created by the lower-multiplier containers in round 2 shifted the overall mindset of participants, making the high multiplier containers the most profitable. We chose two containers, and once again received an average payoff from this challenge.

Round 5 – News based market prediction
In the final round, we were given brief news articles for different products and had to predict price movements before market opening. We could trade ahead of the market at a significant fee per product.
Product	Predicted move	Actual move	Fee	Profit & Loss
Haystacks	1%	-0.48%	120	-168
Ranch sauce	5%	-0.72%	3,000	-3,361
Cacti Needle	-32%	-41.2%	122,880	9,105
Solar panels	-11%	-8.9%	14,520	-4,638
Red flags	8%	50.9%	7,680	33,046
VR monocle	13%	22.4%	20,280	8,876
Quantum coffee	-16%	-66.79%	30,720	76,153
Moonshine	-	3%	-	-
Striped shirts	-	0.21%	-	-
Total			199,200	119,013

Our analysis on trying to predict the moves was quite strong. We missed out on massive gains on Red Flags, not quite pricing in the scarcity described in the news article for a high demand asset leading to this large increase in price. This round our overall persistence and intuition led to one of our best performances. 
The manual trading was a strong aspect for us going into the competition with our extensive backgrounds in mathematics, statistics and probability. We learned the importance of understanding other markets participants and their behaviour in the financial markets and trading. We learned to evaluating risk tolerance and use stress-testing and simulations outside an academic environment sharpening our strategic thinking and decision-making under uncertainty.
Skills developed
	Understanding the behaviour of market participants
	Maintaining objective approach under uncertainty
	Applying game theory 
	Using computational tools to analyse outcomes and probabilities

Conclusions
This competition was an excellent learning experience in algorithmic trading. Starting from limited programming knowledge, we progressed to developing and refining complex trading strategies. We learned to apply technical skills to the overall trading process – from market and data analysis to strategic execution and performance evaluation. It is always exciting to compete with other like-minded individuals while applying our academical knowledge into developing real-world skills. Not everything we did was successful, but every success and every failure offered opportunities for growth. This experience has inspired us to continue learning about trading and elevate our coding ability to the new level. 
We want to thank IMC for organising this challenge. It gave us valuable experience and new fresh insights on what skills are important for success in trading and in the financial markets.
![image](https://github.com/user-attachments/assets/236ab44a-6a5b-4263-b9b1-557bfa3c2c0a)
