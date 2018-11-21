# Exploration of software in the large
## Popular?
The Guava library is a “popular” library. There are 2409 people watching this library, it means 2409 people are following this library and getting notification about it,  28049 star means 28049 people saved guava as a bookmark, and 6344 forks, 6344 people get a copy of this library. Also, there have been 4840 commits, 5 branches, and 83 release created. There are 167 contributors in the Guava library.

## Readme file
Inside the readme.md file, The raw gives a raw view of text. The blame show each line in file and who work on each line. History shows all the commit and changes for this file. If one click the raw button, the Markdown syntax is shown. For example, we can see that one # is used before the largest heading text, and ## is used before the second largest heading and the smallest heading one can set is six # signs. One can use bold, italic or strikethrough text to emphasis something; quote text with a >. We can create link by writing link text in [ ] following by URL in (). We can make unordered lists by putting - or * before the text, use number if we want to order the list and so on. 

## Issues
There are 727 open issues and 2134 closed issues people from the community found in this library, some are resolved and some are still going on. 

* One example of the closed issue is #3316. One person asked if google graphs will still be supported in the future and a member resolved it by saying he will continue to support it. 
* An open issue is #3220, a person suggest to add a reset() method to RateLimiter so everytime a mobile app is log in by a different user it will reset it. One person respond that it will be the same as the method: setRate(sameValueThatWasUsedWhenCreating) but the person who open this issue argued that this method is setting each request to the cost of the previous request. He wants to add a method to solve the problem that the next request have to repay the cost of the previous request. However, another person suggest this might violates the RateLimiter’s contract. Thus, the issue has not been resolved. 

## Pull requests
There are 58 open and 311 closed pull requests. Pull requests are proposed change to the library and some will eventually make it to the master branch after the discussion. Some are in response to an issue and some are standalone pull requests.

* no.#2148 is a standalone pull requests and the opener suggest to extend the byte array indexOf function with start and end limits. This pull request is approved and merge to the ‘master’ because it will make it easier to handle if the data comes from structure the programmer have no control over, such as ByteBuffer from NIO. 

* A pull request responding to an issue is #3213, it’s a respond to the issue #3209 and the link to the issue is in the title of the pull request. In the issue the opener mentions how immutableset and immutablelist can help to optimize the performance for toArray of size zero. One reviewer told him to add a pull request for this improvement, after seeing the proof of the improvement, the pull request was passed. 

## Precondition
Precondition library provides methods that check if methods are invoked correctly. There are a large number of overloaded checkArgument, which ensures the truth of the boolean; checkNotNull(T) which checks the value is not null; and checkState(boolean) method which checks the state of the calling instance but not the parameters. There are also other precondition such as checkElementIndex which make sure the element is valid, checkPositionIndex which ensure the position is valid and checkPositionIndexes which ensures the validation of the sub range.

## Compiling the library
The guava-maven is different from other library because it has its own library. The directory structure created by maven is usually src/main/java, src/main/resources as application/library sources. When compiling Guava, its library sources are src/com/google/collect... because it has its own google core libraries for java, Guava Testing Library, Unit Tests and GWT compatible libs. It also has its own guava-test-gwt-sources. 

## Test cases
In the EquivalenceTesterTest.java class, it first check the set is null, then it uses expectequivalent, expectdistinct, and expectHash methods to compare if the two object is the same or different. The test also checks if the relation’s symmetry, transitiveness and inequivalence.

### Small issue
We can add a reflexive method to the EquivalenceTesterTest class because for a relation to be equivalence, the elements of a set should be reflexive, symmetric, and transitive. This test class has symmetric and transitive methods but not reflexive. A relation is reflexive if and only if for each x∈ R,  (x,x)∈R. So every elements in the set needs to have a reflexive set, but for a relation to be symmetric or transitive, it is enough for it to be symmetric or transitive if only one relation satisfy. To make this change, I need to do the following:
* Create a new issue describing the problem
* Discuss with people from the community and communicate the problem with them.
* If the conversation went well and people agreed this problem, create a new pull request. 
* After review by reviewers and if approved, commit and merge the added code to the class. The reviewer will pass checks and check if the branch has any conflicts wuth the base branch.