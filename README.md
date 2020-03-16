# LeetCode-Activity
Integer to Roman Numeral Code and Description

Convert Integers to Roman Numerals


I am currently teaching AP Computer Science A (my first year), and I chose this assignment because I thought it was something that my students could also code.  We just learned about user-defined classes, and ArrayLists, and I thought I could code this using both.

First, I created a String array containing the “pivotal” Roman numeral values, and an integer array containing their corresponding integer value.  Within a “for” loop, I then compared the inputted integer to the numbers in the integer array.  Once I found a number in the integer array that was greater than the input value, I used division to determine the quantity of Roman numeral values that would be needed to represent that number.  (For example:  if the input number was 32, when I divided by 10 I would get 3 as my dividend, and that would mean we need 3 X’s – XXX).  I then continued this loop using the remainder until the dividend became 0.

Runtime Analysis (6ms/5ms)
The first time I completed the activity, it had a runtime of 6ms.  After further reviewing my code, I noticed that I had an unnecessary "while" loop.  

I believe that I could have a better runtime and less memory usage if I used strings to store my Roman numeral values rather than an array.  However, I purposely used these because arrays are topics that my classes need practice with.


class Solution {
  
    private int divnum = 0;
    private int newnum = 0;
    String romanstr = "";
    int []values = new int [] {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
    String [] romans = new String [] {"M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"};
  
    public Solution(int num)  
    {
       newnum = num;
    }
    
    public String intToRoman ()
    {

        for (int i = 0; i < values.length; i++)
        {
         if (newnum >= values [i])
         {
           divnum = newnum / values [i];
  
           for (int j = 0; j < divnum; j++)
           {
             romanstr += romans [i];
           }
         }
 
         newnum = newnum % values[i];
 
        }
      return romanstr;
    }
    }
 


		
