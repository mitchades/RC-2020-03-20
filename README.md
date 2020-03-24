# RC-2020-03-20
solutions to the March 20, 2020 Riddler Classic featuring questions about the card game Set

My answers to question 1 and 2 have no great insights. Representing the cards as ternary numbers `0000` through `2222` with each place representing one attribute is an easy first step. (In my programming, I just used the integers 0 to 80 instead of ternary strings or 4D arrays.)

I used a Monte Carlo approach for question 1: finding the maximum number of cards you could have (from a single deck of 81 cards) such that there are no sets among them. It happened to get the same answer that Laurent Lessard found -- **20 cards**.

I made one assumption for question 2 (the largest number of sets one can possibly find among 12 cards) -- all the cards would share one attribute, so I could narrow my search space from an infeasible 81 choose 12 (over 70 trillion) to a more doable 27 choose 12 (over 17 million). Also, due to the symmetry of how the attributes are distributed in the cards, I could assert that the first card I choose is card `0000` and make the place-to-attribute connections after the fact. That got me down to 26 choose 11 (under 8 million). From there, I found the answer was **14 sets**.

Question 3, the probability that a random choice of 12 cards contains at least one set, was easy enough to run a Monte Carlo experiment on. However, I think I found an exact answer. It depends on this hypothesis:

<blockquote>Given a group of cards on the tableau (i.e., that have been played) that already have no matches, the probability that adding a fixed number of cards will make a match is only determined by the number of "outs" in the deck (cards that will make a set with other cards on the tableau).</blockquote>

