# Futures Fair Value Adjustment

A modified calculation approach is presented for the fair value of an equity index futures contract. The modified calculation takes into account the funding required to support the tail hedge that was not considered previously.

1.1	Notation
	
 	The value of the equity index on day t.
 	The prevailing money market interest rate to the term of the future (see https://finpricing.com/lib/IrCurveIntroduction.html). 
 	The present value of dividends to be paid over the term of the future.
 	The number of days from t to expiry of the futures contract.
 	The hedge ratio on day t.
 	The fair value of a futures contract on day t.

2.0	The Single Period Model

The traditional model for a futures contract computes its fair value as

		  (1) ,
which is based on hedging a short futures contract by buying the index, paying the funding upon expiry and receiving dividends over the life of the contract. Given this valuation model, the delta of the futures contract is

		    (2),
implying that the appropriate hedge is  , not  . However, if the correct hedge is   then (1) cannot be the correct pricing model because it explicitly assumes that  , which is only true in the last period. A multi-period model must take into account the cost of funding a non-unitary hedge ratio.

3. The Multi-Period Model

We assume that the arbitrageur wishes to be completely hedged, implying that

	  (3).

In words, the change in the value of the futures contract and funding cost the hedge is equal to the change in the value of the index position. Now upon expiry the value of the futures contract must equal the index value,

	   (4),

and from the derivation of (1) we know that with one period to go the optimal hedge ratio is 1, which leads to: 

		 	(5).

Moving one period back,

	 
or

	  (6),

which must always be true given any value of  . This requires that 

	  
or

	  (7).

Substituting (7) into (6) we solve for   :

	  (8).

By induction,

	    (9)
and

	   (10).

4.0	Numerical Analysis

The attached spreadsheet shows the impact of using the two methods of computing fair value:

	 	(11)

and

	  (12)
	
Assume that the SPX index starts out with a level of 1495, that there are 100 days left to expiry and the current 100 day interest rate is 6%. 

4.1	Old Method

The arbitrageur establishes a short position of 100 futures contracts priced at  and buys $37,997,917 of stock that costs $6,333 to fund overnight. On the next day the index falls to 1485.858, causing the arbitrageur to realize P&L of  $-135. Over the life of the contract, the arbitrageur realizes a loss of $5247.     

4.2 New Method

The arbitrageur establishes a short position of 100 futures contracts priced at   and buys $37,996,751 of equity as a hedge. When the index drops to 1485 the total P&L is 0 as predicted, and over the life of the contract there is no profit or loss, proving the analytics above. 

5	Recommendation

We recommend that the new method be approved in order to determine the fair value of futures contracts for index arbitrage. This is important because the current method undervalues predominantly short futures positions creating erosion of P&L over the life of the contract.


