# lambdacomparator
(in progress) Like the 15 param occamsfuncer universalFunc (which is designed to simple and human intuitive) but is only 6 params and designed to be as simple as possible.

A forge of smashing godel-incompleteness into an epsilon size fraction of the space of all possible functions within the "nonhalters" aka function number 1. Finitely computable 1-to-1 mapping between positive integers and all possible lambda functions (plus 1 more for nonhalters), and guarantee that for any 2 integers, it is verifiable that they have different behaviors on at least 1 possible other integer as its parameter or as function called on it as param, and that no 2 positive integers have the same behaviors. Average constant time, and worst case linear time, implementation of java.util.Comparator&lt;Lambda>, with godel-quality guarantee that for any Lambda x and Lambda y, compare(x,y)==0 (aka x.equals(y)) if-and-only-if forAll z, (x z).equals(y z) &amp;&amp; forAll pairs of b and c where b.equals(c) then (b x).equals(c x), and compare func always halts in worst case linear (of memory used by x and y). Examples will be provided of common algorithms including sub-n-cubed matrix multiply, n * n * log(n)^someSmallConstant editDistance, n * log(n)^someSmallConstant list sort. Representation of a function of unique behavior is a universal lambda of always 6 curried parameters. Its normally considered mathematically impossible to compare lambda functions purely by their behaviors always in finite time, but these are only a specific turing-complete subset of all possible lambdas which all of except 1 (lambda number 1 aka the nonhalter) are pattern-calculus-functions. At a level above that, we can check if a lambda is the nonhalter by it is the lowest sorted lambda and its integer is 1. Lambdas are sorted only by their integers, not their hashcodes, and they do not technically need hashcodes except as an optimization. Comparing is by binary forest shape of call pairs (first by height, then recursively by left child, then recursively by right child). All possible ways of generating a lambda will result in the same integer of lambda. You might call it a difference of semantics whether they are comparable or not, since this equality depends on ability to look at their internal forest shape of call pairs using the getFunc, getParam, and isLeaf opcodes (3 of the 8 opcodes, chosen by the first 3 of 6 params of the universalFunc being leaf or any nonleaf). An equals function already exists in occamsfuncer, which is a more complex universalFunc that always takes 15 (instead of 6) params and is designed to be more intuitive for people to do functional programming with and probably more optimizable. This 6 param function is more like something you'd find in a math book or research but will be scaleable enough to use trillions or more of them in realtime in a high security peer to peer network or to email secure executable functions and pieces of any kind of data to eachother without the possibility of viruses since their only permission is (integer,integer)->integer. They are a kind of number and can only see and create/find numbers. Such numbers can be more efficiently referred to by a merkle hash of the binary forest of call pairs (with up to 128 bits of literal data in each whose childs are (pair x) and y, where x and y are each 64 bits of literal data, and so on down to true or false being each bit and so on down to the universalFunc of always 6 curried params. So you might get an email containing 256 bit numbers and their 2 256 bit childs which each refer to a specific lambda of a specific integer (where lambda number 1 is nonhalters, lambda number 2 is the universalFunc, lambda number 3 is universalFunc called on itself), and so on for every possible halted binary forest of call pairs.

...the first 3 of which choosing between these 2^3 uses of the last 3 params depending on if each of the first 3 params isLeaf or not: La.Lb.Lc.Ld.Le.Lf.(getFunc f), La.Lb.Lc.Ld.Le.Lf.(getParam f), where ((getFunc x)(getParam x)) aka (getFunc x (getParam x)) equals x for all x (including combos of halters and nonhalters but derived equals function only halts when called on 2 funcs which are both not nonhalter, and if either is nonhalter then (after infinite time, or finite time if you have infinite memory which the universe and black hole computers do) returns nonhalter), La.Lb.Lc.Ld.Le.Lf.e aka true (aka the K lambda of SKI calculus) if 2 curries left, La.Lb.Lc.Ld.Le.Lf.f aka identityFunc and false depending if theres 1 or 2 curries left, La.Lb.Lc.Ld.Le.Lf.(isLeaf f) aka true or false depending if f is the universal func (where all paths in the forest lead to) or not, La.Lb.Lc.Ld.Le.Lf.((d f)(e f)) aka (d f (e f)) aka the S lambda of SKI calculus, La.Lb.Lc.Ld.Le.Lf.fde (aka pair lambda as in church encoding), La.Lb.Lc.Ld.Le.Lf.d(pair (a b c d e) f) which is used for recursion and vararg lambdas accumulating linkedlist (made of pairs etc) in e and f is next incoming lambda and d chooses to eval it vs keep currying (implemented using only combos of these 8 ops aka a universal function)... Comparator is first by height of binary forest, with base case of height 0 for the universal func aka leaf. If equal, then break ties by comparing left child, if equal then break ties by comparing right child. It cant be equal beyond that since it would have been equal at binary forest parent, optimized by hash-consing equality. A function is halted if itself and every child recursively has at most 5 curried params (as its a universal func that always curries 6 params). The 1-to-1 mapping between unique function behaviors and positive integers is the sorted order of such binary forests excluding any which are nonhalted, after nonhalter (normed form of all nonhalting lambda calls, all equalling eachother) which is integer 1. (getFunc leafAkaTheuniversalfunc) equals identityFunc (aka false called on leaf). (getParam leafAkaTheuniversalfunc) equals leafAkaTheuniversalfunc. The "plus 1 more for nonhalters" is the normalized form of any function call which never halts (which I'm not saying I can calculate in finite time, but in abstract math it does complete the (integer,integer)->integer space of every possible lambda is an integer, and called on a lambda (an integer), ALWAYS returns an integer (if you have cached every possible func param return triple, which can be verified in a pigeonhole-like way using the constraints of the 8 ops timelessly, in theory at least). The actual existence and practicality of java.util.Comparator<Lambda> can be demonstrated (TODO) by using secureHash of every binary forest node, along with a certain constant representing nonhalting, where (nonhalter nonhalter)->nonhalter and (nonhalter anyHalted)->nonhalter and (anyHalted nonhalter)->nonhalter and (anyHalted someHalted)->[either nonhalter or a specific halted as the universal lambda func defines]. The transfinite hashcode, with exactly 0 collisions, uniqely identifying every lambda function by content (even without knowing which integer it is, which can be computed in finite time but this could be much faster in some well ordered combos), is a hash function of any finite set of functions and is the xor of doesItHalt(x,y) for every ordered pair x y among the set s, such as if its a set size 2 then its the xor of 2 things, or if its a set size 3 then its the xor of 3!=6 such calls, returning true or false, and such hash function always halts even if called on combos of halting and nonhalting lambdas (if cached in a space of infinite size such as the cardinality of real numbers, and practically, we might statistically converge toward agreement of such bit of hash between each pair of 256 bit merkle hash of binary forest by the math property that this undirected unweighted graph whose nodes are the set of all possible unique lambda functions plus one function representing nonhalting... the math property that it has exactly 1 automorphism aka itself, that no permutation of it equals itself, and that it is an infinite size undirected graph which contains every finite size undirected graph an infinite number of times and in every possible combo of them.

API will be something like...

public interface Lambda implements Comparable < Lambda > {
    public Number integer(); //finite but low polynomial (and big nonscaleable) cost, mostly for math proofs
}
  
public class FuncParamReturn{
   public final Lambda func, param, ret;
}

//use Map<FuncParamReturn,Double> or bloomFilter of FuncParamReturn -> [isCertainlyTrue, isCertainlyFalse] or bloomFilter of unorderedPair([funcX,funcY])->[isCertainlyTrue, isCertainlyFalse], etc, to converge in p2p network toward together optimized computing of [func,param,return] and dedup of lambdas, gradually removing paradoxes from the network based on the perfect godel-like numbering of functions of a type that are slightly lower cardinality than turingComplete (aka slightly lower cardinality than exponential of NP) and greater cardinality than exponential of BQP... is my first guess of how to describe the cardinalities.
 

 
This is 1 of the lambdas/integers of an infinitely perfect 1-to-1 mapping between positive integers and
every possible lambda function (by its behaviors only, including others behaviors when called on it),
where you can always in finite time convert between integer and lambda.
It is a pure math function of (integer,integer)->integer which is well defined for every positive integer
called on every positive integer and every such pair returns a positive integer
if you have infinite time to wait to see if it halts or not
and if it does not halt then it returns 1 and it does halt then it returns an integer greater than 1.
Examples: (1,1)->1. (1,anything)->1. (anything,1)->1. (2,2)->3.
2 is the universalFunc. 3 is the universalFunc called on itself.
There is some integer which represents the exact value of pi, for example,
as a function of (some encoding of) integer to bit (true or false).
One possible encoding of integers is a linkedlist of true or false.
Pair, true, false, and identityFunc are very small integers, and so are lispCons, lispCar, lispCdr, lispNil.
This system is capable of turing-complete compression of anything, in theory, such as that sound thats
like an "optical illusion" that has a constant average frequency but keeps sounding like its decreasing in frequency
due to a bunch of notes fading in at higher frequency and gradually lowering in frequency while fading out
of amplitude over time shaped similar to a bellcurve.
Such compression could be done by mixing a representation of binary forest
(how many nodes back is my left and my right child, or how many bytes back, etc)
with a prefix that means to start a literal bitstring of a powOf2 size, in lambdas
represented as a complete binary tree of true or false at its leafs padded by true/1 then falses/0s until the next powOf2
to represent a bitstring of any length. This AIXI level of generality of compression
would be a data format but not the algorithm to find better compressions unless you have exponential time
to loop over them all up to a certain bit length OR if you have a really smart AI.
You could even, in theory, compress a superintelligent AI by referring to testcases of its intelligence
and to loop over all possible AIs and return the first one that passes all the testcases
BUT the cost of decompressing it would be exponential, so even though you could know for sure
that what you have is a compressed file containing a superintelligent AI,
you would not be able to practically decompress it or know anything about it other than
that it is the first one in the defined loop that passes all those testcases you gave,
similar to that AIXI is a math model of intelligence but to actually use it cost exponential or maybe up to infinite time,
and despite that there are some very weak approximations. 
*/
public interface Lambda extends Comparable<Lambda>, UnaryOperator<Lambda>

NumInts = quantity of positive integers. This is not itself an integer but is a statement somehow related to cardinality. Cardinality is a part of math that I've never fully understood or believed in, likely cuz its not entirely consistent.

//funcallCache[func][param][return][numComputeCyclesBeforeReturn_plusSomeSmallConstant_Or1IfReturns1][twoBitsForIsItCertainlyTrueOrCertainlyFalse]
//funcallCache is a 4 dimensional bloomFilter with 2 bits in each cell. Those bits are 00 for unknown, 10 or 01 for false or true (todo opposite order?), and are never 11 (error, but if 11 occurs then fork the peer to peer approximation of this bloom filter so that 11 doesnt occur).
funcallCache = bit[NumInts][NumInts][NumInts][NumInts][2];

Statements are of the form: func called on param returns ret in numComputeCycles unoptimized compute cycles.
funcallCache contains every such possible statement, both a claim that its true, claim that its false, or lack of either claim.

A statement can not be negated, such as it is NOT true that (x y)->z. You can only say (x y)->z in c cycles for any positive integers x y z c. This is more limited than godel numbering and halting oracles etc.

A statement can be represented as a negative integer in some ordering of the 5d infinite size array such as cantor diagonals or hex digits with a high 1 bit (except excluding any duplicates im not too sure about that one) or any encoding you like (TODO choose one).

Every statement is certainly false or certainly true, but that doesnt mean you know it.

For every false statement, there exists a negative integer which disproves it in finite time.
For every x y, there is a statement that x called on y never halts.
For every x y c r, there is a statement that x called on y returns r in c compute cycles (plus small constant so 1 is the nonhalter). If c is infinity, then c is 1. 1 is the normalized form of all nonhalting lambda calls.

For every x y, there exists exactly 1 true statement of the form x y c r which are some 4 positive integers.

If a call is claimed to never halt but thats false, it can be disproven in finite time by emulating each next compute step which eventually halts.

If a call is claimed to never halt and thats true, then it cant be disproven. It is still true that each false statement can be disproven in finite time (per false statement).

If a call is claimed to halt a certain way (returns r in c compute cycles) and that is true, it can not be disproven.

If a call is claimed to halt a certain way (returns r in c compute cycles) and that is false, it can be disproven in finite time by either finding what it does halt on before c cycles or finding that after c emulated cycles it has not halted.

Therefore all false statements can be proven false in finite time, and no true statements can be disproven, and no statements exist about proving the truth or falseness of statements which godel tangles and so on.

Therefore in the 5d matrix of bits, of infinite size in each of 4 dimensions and size 2 in the other, the constraints allow for only 1 possible bit value in each 5d cell, and if we sample from the powerset of all such possible 5d matrixs and converge this for up to every finite time (but not up to any infinite time, kind of epsilon distance below that), every such possible matrix except 1 is disproven, and it is my belief that the world around us is the only one which could not be disproven because it just happened to contain all possible true statements and no false statements, or more practically that as many such approximate converging sparse matrixs partially overlap, they are, in theory, hill-climbable out of every local energy minimum with no saddlepoints, concavity, but the space of all turing complete possibilities is so huge that you could get lost in near equal directions for a very long time.
