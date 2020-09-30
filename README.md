# lambdacomparator
A forge of smashing godel-incompleteness into an epsilon size fraction of the space of all possible functions within the "nonhalters" aka function number 1. Finitely computable 1-to-1 mapping between positive integers and all possible lambda functions (plus 1 more for nonhalters), and guarantee that for any 2 integers, it is verifiable that they have different behaviors on at least 1 possible other integer as its parameter or as function called on it as param, and that no 2 positive integers have the same behaviors. Average constant time, and worst case linear time, implementation of java.util.Comparator&lt;Lambda>, with godel-quality guarantee that for any Lambda x and Lambda y, compare(x,y)==0 (aka x.equals(y)) if-and-only-if forAll z, (x z).equals(y z) &amp;&amp; (z x).equals(z y), and compare func always halts in worst case linear (of memory used by x and y). Examples will be provided of common algorithms including sub-n-cubed matrix multiply, n * n * log(n)^someSmallConstant editDistance, n * log(n)^someSmallConstant list sort. Representation of a function of unique behavior is a universal lambda of always 6 curried parameters

...the first 3 of which choosing between these 2^3 uses of the last 3 params depending on if each of the first 3 params isLeaf or not: La.Lb.Lc.Ld.Le.Lf.(getFunc f), La.Lb.Lc.Ld.Le.Lf.(getParam f), where ((getFunc x)(getParam x)) aka (getFunc x (getParam x)) equals x for all x (including combos of halters and nonhalters but derived equals function only halts when called on 2 funcs which are both not nonhalter, and if either is nonhalter then (after infinite time, or finite time if you have infinite memory which the universe and black hole computers do) returns nonhalter), La.Lb.Lc.Ld.Le.Lf.e aka true (aka the K lambda of SKI calculus) if 2 curries left, La.Lb.Lc.Ld.Le.Lf.f aka identityFunc and false depending if theres 1 or 2 curries left, La.Lb.Lc.Ld.Le.Lf.(isLeaf f) aka true or false depending if f is the universal func (where all paths in the forest lead to) or not, La.Lb.Lc.Ld.Le.Lf.((d f)(e f)) aka (d f (e f)) aka the S lambda of SKI calculus, La.Lb.Lc.Ld.Le.Lf.fde (aka pair lambda as in church encoding), La.Lb.Lc.Ld.Le.Lf.d(pair (a b c d e) f) which is used for recursion and vararg lambdas accumulating linkedlist (made of pairs etc) in e and f is next incoming lambda and d chooses to eval it vs keep currying (implemented using only combos of these 8 ops aka a universal function)... Comparator is first by height of binary forest, with base case of height 0 for the universal func aka leaf. If equal, then break ties by comparing left child, if equal then break ties by comparing right child. It cant be equal beyond that since it would have been equal at binary forest parent, optimized by hash-consing equality. A function is halted if itself and every child recursively has at most 5 curried params (as its a universal func that always curries 6 params). The 1-to-1 mapping between unique function behaviors and positive integers is the sorted order of such binary forests excluding any which are nonhalted, after nonhalter (normed form of all nonhalting lambda calls, all equalling eachother) which is integer 1. (getFunc leafAkaTheuniversalfunc) equals identityFunc (aka false called on leaf). (getParam leafAkaTheuniversalfunc) equals leafAkaTheuniversalfunc. The "plus 1 more for nonhalters" is the normalized form of any function call which never halts (which I'm not saying I can calculate in finite time, but in abstract math it does complete the (integer,integer)->integer space of every possible lambda is an integer, and called on a lambda (an integer), ALWAYS returns an integer (if you have cached every possible func param return triple, which can be verified in a pigeonhole-like way using the constraints of the 8 ops timelessly, in theory at least). The actual existence and practicality of java.util.Comparator<Lambda> can be demonstrated (TODO) by using secureHash of every binary forest node, along with a certain constant representing nonhalting, where (nonhalter nonhalter)->nonhalter and (nonhalter anyHalted)->nonhalter and (anyHalted nonhalter)->nonhalter and (anyHalted someHalted)->[either nonhalter or a specific halted as the universal lambda func defines]. The transfinite hashcode, with exactly 0 collisions, uniqely identifying every lambda function by content (even without knowing which integer it is, which can be computed in finite time but this could be much faster in some well ordered combos), is a hash function of any finite set of functions and is the xor of doesItHalt(x,y) for every ordered pair x y among the set s, such as if its a set size 2 then its the xor of 2 things, or if its a set size 3 then its the xor of 3!=6 such calls, returning true or false, and such hash function always halts even if called on combos of halting and nonhalting lambdas (if cached in a space of infinite size such as the cardinality of real numbers, and practically, we might statistically converge toward agreement of such bit of hash between each pair of 256 bit merkle hash of binary forest by the math property that this undirected unweighted graph whose nodes are the set of all possible unique lambda functions plus one function representing nonhalting... the math property that it has exactly 1 automorphism aka itself, that no permutation of it equals itself, and that it is an infinite size undirected graph which contains every finite size undirected graph an infinite number of times and in every possible combo of them.

API will be something like...

public interface Lambda implements Comparable<Lambda>{
    public Number integer(); //finite but low polynomial (and big nonscaleable) cost, mostly for math proofs
}
  
public class FuncParamReturn{
   public final Lambda func, param, ret;
}

//use Map<FuncParamReturn,Double> or bloomFilter of FuncParamReturn->[isCertainlyTrue, isCertainlyFalse] or bloomFilter of unorderedPair([funcX,funcY])->[isCertainlyTrue, isCertainlyFalse], etc, to converge in p2p network toward together optimized computing of [func,param,return] and dedup of lambdas, gradually removing paradoxes from the network based on the perfect godel-like numbering of functions of a type that are slightly lower cardinality than turingComplete (aka slightly lower cardinality than exponential of NP) and greater cardinality than exponential of BQP... is my first guess of how to describe the cardinalities.
 
