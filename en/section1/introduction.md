# Why use Jirac ?
Developement and testing are bounded together when it comes to build quality softwares.  
Developers and testers must work together to be the most eficient, and communication is the watchword.  
Various tools exist to reach that goal. [Jira](https://www.atlassian.com/software/jira/#!) is one of them.  
However, no matters how good the tool is, it won't solves lack (or the excess) of informations in comments produced by a human being.  
As usual the problem is between the chair and the keyboard.  
We often have to tackle this issue while correcting a bug or developing a feature.

**The scenario is the following**:  
A bug is noticed by a tester who in return creates a ticket and affects it to a developper (through jira for instance).   
The ticket is treated and returned to the sender with a comment.  
We expect this comment to contain informations such as the changeset (sha1 for Git), the commit branch, the software version, the context of the correction...  
The tester would then be able to test the correction or the feature in the blink of an eye, without questioning. No waste of time.

In reality, this hardly occurs. Usualy, one put the degree of information he thinks relevant.  
Moreover, formating would be too much different from one developper to another to allow an efficient reading.

**Jirac proposes to solve this issue by automating the comment generation to a given ticket**.
By providing concerned commits by the correction or the feature, jirac will output a formated comment giving the right amount of information to the tester for an eficient treatment.
