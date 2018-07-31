## _Try using a `TreeMap` and a `HashMap` instead of `MyHashMap`. Are the resulting word frequencies any different? 
There is no difference in word frequencies between the three `Map` implementations. I did not expect any differences as they all implement the `Map` interface so they should all work the same theoretically.

## Is the time [above] performance any different? If so, how would you rank the three implementations (in increasing order of time complexity)?_
Speeds:
`MyHashMap` = ~351ms
`HashMap` = ~300ms
`TreeMap`= ~433ms

As expected, the `HashMap` is a bit more efficient than the one created by a novice programmer.
## _How are  `%`  and  `Math.floorMod`  different? Which works more reliably for computing a hash table index?_
In this scenario, using `Math.floorMod` will yield a positive remainder where `%` will not. A negative hash index would not work well as we cannot have a table of negative size. Therefore, `Math.floorMod` is more reliable than `%` for computing table indices. 

## _What is the time complexity of  `MyHashMap.size()`, and how could you make it much more efficient?_
The time complexity for the above method is O(n). The `for` loop will execute `table.size()` amount of times, which is n number of elements. To increase efficiency, instead of iterating through the entire table to count all the elements, use an instance variable that is incremented or decremented each time an item is put or removed. Then all the `size()` method would do is return the value of this variable.
## _How does this implementation compare to one where you would directly use your linked  `Node`  class from the earlier assignment? Answer briefly in terms of ease of implementation, correctness, reliability, and performance._
**Implementation:** Working with individual nodes instead of the `List` class would have made the implementation process a bit easier to understand as a `Node` that can contain a `List` as a data field is somewhat more comprehensible than a `List` of `Lists`. 
**Correctness:** I am not entirely sure what is meant by "correctness" but I'll assume that it means something along the lines of "would it work like the interface intends it to" for the sake of answering this question. I think the big hurdle to overcome here is how hash table indices could be applied to individual Nodes. The nodes would have to be routinely rearranged or a predetermined amount created at the start perhaps.
**Reliability** As long as the aforementioned difficulties using `Node` instead of a `List` are accounted for, the `HashMap` should still work as intended. There is nothing about `Node` that inherently makes it less reliable.
**Performance** I imagine that this implementation and the `Node` implementation would perform somewhat similarly. For finding values to return, add, or remove, the methods will still have to iterate through all of the keys until it finds the one specified in the method call.
