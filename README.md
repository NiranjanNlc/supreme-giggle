#  Solution of Problem  Practised 
List of problem i encountered <br>
Write a function that returns the sum of two numbers.
```
fun sumOfTwoNumber(param1: Int, param2: Int): Int {
  return param1+param2
}
```
Given a year, return the century it is in. The first century spans from the year 1 up to and including the year 100, the second - from the year 101 up to and including the year 200, etc
```
fun getCenturyFromYear(year: Int): Int {
  var century = year/100
  if(year%100==0)
  return century
  return century+1
}
```
Given the string, check if it is a palindrome.
```
fun checkPlaindrome(inputString: String): Boolean {
  if(inputString.reversed()==inputString)
  return true
  return false
}
```
Given an array of integers, find the pair of adjacent elements that has the largest product and return that product.
```
fun largestProductAdajcentElements(inputArray: MutableList<Int>): Int {
  var highest=-11111111;
  
  for( i in 0 .. inputArray.size -2)
  {
      val multipied = inputArray.get(i)*inputArray.get(i+1)
      if(multipied> highest)
      highest= multipied
  }
  return highest
}

```
Below we will define an n-interesting polygon. Your task is to find the area of a polygon for a given n.
A 1-interesting polygon is just a square with a side of length 1. An n-interesting polygon is obtained by taking the n - 1-interesting polygon and appending 1-interesting polygons to its rim, side by side. You can see the 1-, 2-, 3- and 4-interesting polygons in the picture below.
```
fun findNoOfPolygon(n: Int): Int {
 var a =1
 var b= 0
 for(i in 1..n)
 {
     a= a+ b
     b= b+ 4
 } 
 
```
Ratiorg got statues of different sizes as a present from CodeMaster for his birthday, each statue having an non-negative integer size. Since he likes to make things perfect, he wants to arrange them from smallest to largest so that each statue will be bigger than the previous one exactly by 1. He may need some additional statues to be able to accomplish that. Help him figure out the minimum number of additional statues needed.
```
fun findMinNoOfStatue(statues: MutableList<Int>): Int {
 var statue = statues.sorted()
 var cnt =0
 for(i in 0 .. statue.size-2)
 {
     val check = (statue.get(i)+1)== statue.get(i +1)
     println(check)
     if(!check)
     cnt = cnt+ statue.get(i+1)-statue.get(i)-1
     println(cnt)
 } 
 return cnt
}

```
Given a sequence of integers as an array, determine whether it is possible to obtain a strictly increasing sequence by removing no more than one element from the array.
Note: sequence a0, a1, ..., an is considered to be a strictly increasing if a0 < a1 < ... < an. Sequence containing only one element is also considered to be strictly increasing.
```
fun checkForAlmostIncreasingSequence(a: MutableList<Int>): Boolean {
//   if(a.sorted()==a)
//   return true
    var  count1 = 0 
    var  count2 = 0;
    for(  i in 0 .. a.size-2)
    {
        if(a[i] >= a[i+1]) count1++;
    }
    for(  i in 0 .. a.size-3)
    {
        if(a[i] >= a[i+2]) count2++;
    }

     return (count1 <=1) && (count2 <= 1);
}
```
After becoming famous, the CodeBots decided to move into a new building together. Each of the rooms has a different cost, and some of them are free, but there's a rumour that all the free rooms are haunted! Since the CodeBots are quite superstitious, they refuse to stay in any of the free rooms, or any of the rooms below any of the free rooms.
Given matrix, a rectangular matrix of integers, where each value represents the cost of the room, your task is to return the total sum of all rooms that are suitable for the CodeBots (ie: add up all the values that don't appear below a 0).
```
fun getNumberOfSuitableRoom(matrix: MutableList<MutableList<Int>>): Int {
 var s = 0 
 var x = mutableListOf<Int>()
 for(i in 0 .. matrix.size -1)
 {
  var initRow = matrix.get(i)
      for(j in 0 .. initRow.size -1  )
      { 
          var checkSutia=initRow.get(j)
          println(checkSutia)
          if(checkSutia!=0 && !x.contains(j))
          {
              s= s+ checkSutia
          } 
          else
          {
              x.add(j)
          }
          }
 }
 return s
} 
```







