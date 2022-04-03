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

