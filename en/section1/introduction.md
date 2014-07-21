# Why use Jirac ?
Developement and testing are bounded together when it comes to build quality software.  
Developers and testers must work together to be the most efficient, and communication is the watchword.  
Various tools exist to reach that goal. [Jira](https://www.atlassian.com/software/jira/#!) is one of them.  
However, no matter how good the tool is, it won't solve the lack (or the excess) of information in comments produced by a human being.   
We often have to tackle this issue while correcting a bug or developing a feature.

**The scenario is the following**:  
A bug is noticed by a tester who in return creates a ticket and affects it to a developer (through jira for instance).   
The ticket is solved and returned to the sender with a comment.  
We expect this comment to contain informations such as the changeset (e.g: SHA1), the commit branch, the software version, the context of the correction...  
The tester would then be able to test the correction or the feature in the blink of an eye, without questioning. No waste of time.

In reality, this hardly occurs. Usually, one put the degree of information he thinks relevant.  
Moreover, formatting would be too much different from one developer to another to allow an efficient reading.

**Jirac proposes to solve this issue by automating the comment generation to a given ticket**.
By providing concerned commits by the correction or the feature, jirac will output a formatted comment by giving the right amount of information to the tester for an efficient worklow.