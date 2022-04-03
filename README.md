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
Given an array of strings, return another array containing all of its longest strings.
```
fun getArrayOfLongestString(inputArray: MutableList<String>): MutableList<String> {
  var length1 = 0
inputArray.forEach{
    if(it.length > length1) length1 = it.length
}
return inputArray.filter{ it.length == length1}.toMutableList()
}
```
Given two strings, find the number of common characters between them.
```
fun solution(s1: String, s2: String): Int {
 
 var counter = 0
 s1.toList().intersect(s2.toList()).forEach { 
     x -> counter += listOf(s1.toList().count {it == x},s2.toList().count {it == x}).min()!! 
     }
return counter
}
```
Ticket numbers usually consist of an even number of digits. A ticket number is considered lucky if the sum of the first half of the digits is equal to the sum of the second half.

Given a ticket number n, determine if it's lucky or not
```
fun solution(n: Int): Boolean {
 var n1 = n
 var s1=0 
 var s2= 0
  var luckCalc = mutableListOf<Int>()
  while(n1 > 0)
  {
      luckCalc.add(n1%10)
      println(" ${n%10} addde from ${n1}" )
      n1 = n1/10
  }
  val lngth = luckCalc.size
  for ( i in 0 .. lngth -1 )
  {
      if(i <= lngth/2-1) s1 += luckCalc.get(i)
      else s2 += luckCalc.get(i)
      println( " $s1  $s2 ${luckCalc.get(i)}")
  }
  if(s1==s2) return true
  return false
}
```
Some people are standing in a row in a park. There are trees between them which cannot be moved. Your task is to rearrange the people by their heights in a non-descending order without moving the trees. People can be very tall!
Example
For a = [-1, 150, 190, 170, -1, -1, 160, 180], the output should be
solution(a) = [-1, 150, 160, 170, -1, -1, 180, 190].
```
fun solution(a: MutableList<Int>): MutableList<Int> {
var required = a.filter { it!=-1 }.sorted().toMutableList()
var returnig = mutableListOf<Int>()
var x = 0  
for( j in 0 .. a.size -1 )
{
    if(a.get(j)==-1) returnig.add(-1)
    else 
    {
        returnig.add(required.get(x))
        x= x+1
    } 
}
 return returnig
}
```
Write a function that reverses characters in (possibly nested) parentheses in the input string.

Input strings will always be well-formed with matching ()s.
```
String solution(String str ) {
    var len = str.length();
    Stack<Integer> st = new Stack<Integer>();
    for (int i = 0; i < len; i++)
    {
       
      // Push the index of the current
      // opening bracket
      if (str.charAt(i) == '(')
      {
        st.push(i);
      }
       
      // Reverse the substring starting
      // after the last encountered opening
      // bracket till the current character
      else if (str.charAt(i) == ')')
      {
        char[] A = str.toCharArray();
        reverse(A, st.peek() + 1, i);
        str = String.copyValueOf(A);
        st.pop();
      }
    }
     
    // To store the modified string
    String res = "";
    for (int i = 0; i < len; i++)
    {
      if (str.charAt(i) != ')' && str.charAt(i) != '(')
      {
        res += (str.charAt(i));
      }
    }
    return res;
}

static void reverse(char A[], int l, int h)
  {
    if (l < h)
    {
      char ch = A[l];
      A[l] = A[h];
      A[h] = ch;
      reverse(A, l + 1, h - 1);
    }
  }
```








