# Bayes_COVID
Exploring COVID-19 tests through Bayes

===

 ## Bayesian Funk
Life in the 2020s started off rather rough, as I'm sure you are all aware. When COVID-19 struck, it seemed the world shut down. Questions abounded, regarding the nature of the illness, how it spreads, how deadly it is, and how to remain safe. In the face of immense uncertainty, various businesses closed, and schools were forced to haphazardly improvise online curricula. Some didn't trust the tests and felt that even if they did receive a negative, they would sooner trust their symptoms than the result. Others were the opposite; they were so distrustful of the tests that given a positive result, they would simply ignore it. These concerns were magnified with the introduction of the rapid tests, which gave results in as little as 15 minutes.

Inspired by this, I've decided to take a look at the "accuracy" of the tests
For fun, let's find these probabilities for each other test on that site. I sped up this process using Python, and the code for the process (as well as everything else that follows) can be found on GitHub. Here are my results in a table:
Table of probabilities for each test.Here are those same results, but as pretty graphs:
Finally, let's suppose that a given individual took two tests at the same time and that one test came back positive and the other negative.
Here, we assume that the two test results are independent of each other, meaning that the result of one has no bearing on the result of the other. This necessary as it allows us to decompose the probability of two events occurring at once into two terms. Specifically:
Given that events A and B are independent.
With this in mind, let's calculate the probability in question.
Note that as P(+) + P(-) = 1, then P(-) = 1 - P(-)The news is good. Given both a negative and a positive test, the chances of having the virus shrink to a mere 3%. This seems to imply that negative tests do more to sway your chances of having the virus than positive tests. This makes sense, as a positive test brought you to a mere 87% of having the virus. Meanwhile, a negative test brings you to a whopping 99.8% of not having the virus.
One might think that this is due to the fact that this test has a higher specificity than it does sensitivity. In reality, this is likely caused by the fact that the prior probability of having the virus is relatively low (only 17%). Bayesians call this number the "prior", referring to the prior probability of some event before the new information (from the test results, in this case) comes into consideration.
To prove that the small number found above results from the relative smallness of the prior, I took a look at the chance of having the virus given a positive and negative test result for priors ranging from 10% (0.10) to 90% (0.90) and for every test in the above table. Essentially, this graph imagines what things would look like if 10% of all people had the virus, 90% of all people had the virus, and every precentage in between. These are the results:
As is clear, a higher prior leads to a higher probability of having the virus when given conflicting test results.So that settles that!
Overall, the moral of the story is to trust tests. Chances are that the result given to you by the lab is reflective of your actual status as a carrier (or not) of the virus. If you do decide to get a second test (and receive conflicting information), refer to the above to know how to proceed. At that point, your chances of having the virus heavily depend on your prior probability (represented here as a percentage of the nation with the virus).
