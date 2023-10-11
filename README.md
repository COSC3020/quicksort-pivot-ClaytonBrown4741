[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11857712&assignment_repo_type=AssignmentRepo)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.  

ANSWER:
For this question, I looked at my resources and realized that I could essentially split the possibilities for a pivot choice into  
3 different cases: L (probability of 1/4) M (probability of 1/2) and R (probability of 1/4). In these cases, the M section represents  
a good pivot value while L and R represent the bad pivot values. Using this information, I decided to go through and find out exactly  
how many different combinations resulted in a bad pivot value.  
To begin, I found that if all 3 of the choices for the pivot fell into either L or R, then the Pivot Value would be bad. The probability of  
this would be 1/4 * 1/4 * 1/4, so 1/64. However, we must take into account the numerous different combinations of choices that exist. These  
combinations are listed below:  
L * L * L  
L * L * R  
L * R * L  
R * L * L  
R * R * L  
R * L * R  
L * R * R  
R * R * R  
Because there are 8 combinations, that means that they comprise (1/64) * 8 of the possibilities. This comes out to 1/8 or 12.5%  
However, these aren't the only circumstances where a bad choice is possible. There can also be a bad choice if 2 of the picks are  
in *either* L or R (not both) and 1 of the picks is in M. The probability of a single one of these combinations happening is  
1/4 * 1/4 * 1/2 or 1/32. With this in mind, we can combine our options to get the following combinations:    
L * L * M  
L * M * L  
M * L * L  
R * R * M  
R * M * R  
M * R * R  
This gives us a total of 6 combinations, which means they comprise (1/32) * 6. This comes out to 3/16 or 18.75%.  
If we combine the percentages from all of the combonations listed above, we get a chance of 31.35% of picking a bad  
pivot. As a result, this means we will have a 68.75% chance of picking a good pivot. This is noticeably better odds  
than when only picking one pivot at random, so it can be confidentally stated that choosing the median of 3 randomly  
chosen values will give you better odds than only picking 1 randomly chosen value.
