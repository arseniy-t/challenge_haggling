# challenge_haggling
My solution for [hola! JS Challenge Summer 2018: Haggling](https://github.com/hola/challenge_haggling)

## Strategy for accepting an offer
Accept an offer if it costs greater than or equal to the threshold, which is calculated as:

**threshold** = **total** - 1.7 **round**,

**round** = [0, max_rounds)

**Exception for last round:** if our turn is last accept any offer if it costs more than zero.


## Strategy of making offers
Before all games for each set of object's counts and valuations and each round to calculate offers. When the game start the agent loads this previously calculated offers and uses them.

### Algorithm for calculation of the sequence of offers
We suppose that an opponent on average has a strategy of offers acceptance: «accept an offer if it costs more or equal to the half». We use complete enumeration of the sequences from max_rounds offers for maximization of mathematical expectation of the special game. In this game our agent only makes offers and our opponent only accept or refuse offers. All possible sets of opponent's objects valuation according to the constraints of the generator are assumed equally likely. So this mathematical expectation equals total score in games with each possible opponent's objects valuation divided by the number of these games. When we use complete enumeration we exclude zero and total offers, and exclude offers containing objects which is worth zero for us.
