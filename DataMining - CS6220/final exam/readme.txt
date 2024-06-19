Final Exam CS6220 ReadMe
Nickhil Tekwani

Problem 1 - implement a KNN classifier to classify noisy images
Ideas:
- use cosine similarity for distance metric (generally robust to noise), define using standard numpy library
- use PCA to reduce noise and dimensionality, after a couple tests retaining 40 components seemed to make sense
- k=20 seems to be a solid number of neighbors for acceptable classification accuracy 
Results:
- achieved 78.55% (at least 75% as requested in class)
- cosine and PCA were the right choices for distance metric and feature reduction 
- other preprocessing could be explored, but am happy with this for this exam and requirements 
Other Thoughts:
- could explore manhattan or minkowski as alternate distance metrics
- try gaussian filtering for noise reduction
- would have to use validation data to avoid overfitting

Problem 2 - quiz difficulties mixture using EM
Ideas:
- expectation maximization also works well here as we have observed data (student grades), missing data (quiz version), and parameters (quiz outcome prob + session quiz selection prob)
- represent grades in ternary fashion due to 3 outcomes
Implementation:
- e step, computer expected counts receiving quiz based on initialized probability. this helps estimate how current prob aligns w/ observed data
- m step, update the probabilities based on the expected count. Needed to normalize values to ensure probabilities added up to 1
- utilized a convergence criteria
Results:
pi: (.63, .37)
q_A: (.64, .21, .15)
q_B: (.3, .42, .28)
- these are satisfactory in terms of closeness to the numbers given in class
Considerations/Parameters:
- convergence set at 1e-6 to balance precision and efficiency 
- iterations run until convergence 
- we assumed students are independent of each other, which simplified the calculations as well

