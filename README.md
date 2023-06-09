Download Link: https://assignmentchef.com/product/solved-natural-language-assignment-4-decision-list-classifier
<br>
Write a Perl program called decision-list.pl that implements a decision list classifier to perform word sense disambiguation.

Your program should use as many of the features as you think will result in an accurate classifier. Please make sure you only identify features from the training data, and that you clearly explain what features you are using in your detailed comments.

Your classifier should run from the command line as follows:

perl decision-list.pl line-train.txt line-test.txt my-decision-list.txt &gt; my-line-answers.txt

or

python3 decision-list.py line-train.txt line-test.txt my-decision-list.txt &gt; my-line-answers.txt

This command should learn a decision list from line-train.txt and apply that decision list to each of the sentences found in line-test.txt in order to assign a sense to the word line. Do not use line-test.txt in any other way (and only identify features from line-train.txt). Your program should output the decision list it learns to my-decision-list.txt. You may format your decision list as you wish, but please make sure to show each feature, the log-likelihood score associated with it, and the sense it predicts. The file my-decision-list.txt is intended to be used as a log file in debugging your program. Your program should output the answer tags it creates for each sentence to STDOUT. Your answer tags should be in the same format as found in line-key.txt.

line-train.txt contains examples of the word line used in the sense of a phone line and a product line where the correct sense is marked in the text (to serve as an example from which to learn). line-test.txt contains sentences that use the word line without any sense being indicated, where the correct answer is found in the file line-key.txt. You can find line-train.txt and line-test.txt in the files section of our site in a compressed directory called line-data.zip.

Your program decision-list.pl should learn its decision list from line-train.txt and then apply that to line-test.txt.

You should also write a utility program called scorer.pl which will take as input your sense tagged output and compare it with the gold standard “key” data which I have placed in the Files section of our group (line-key.txt). Your scorer program should report the overall accuracy of your tagging, and provide a confusion matrix similar to the one found on page 156 of JM.  This program should write output to STDOUT.

The scorer program should be run as follows:

perl scorer.pl my-line-answers.txt line-key.txt

or

python scorer.py my-line-answers.txt line-key.txt

You can certainly use your scorer.pl program from the previous assignment as a foundation for this program.

Both decision-list.pl and scorer.pl should be documented according to the standards of the programming assignment rubric.

In decision-list.(pl|py) : include your accuracy and confusion matrix into the comments. And compare your results to that of the most frequent sense baseline.

Please submit your program source code (decision-list.(pl|py) and scorer.(pl|py)) as well as a script file called decision-list-log.txt that you should create as follows :

%script decision-list-log.txt

%perl decision-list.pl line-train.txt line-test.txt my-decision-list.txt &gt; my-line-answers.txt

%head -50 my-decision-list.txt

%head -10 my-line-answers.txt

%perl scorer.pl my-line-answers.txt line-key.txt

%exit

If you are using windows let me know and we can come up with something different.








