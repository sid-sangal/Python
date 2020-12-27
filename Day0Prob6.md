Key takeaways: ndex blank = first element, index -1 = last element
         index must be an integer and we cannot use len(string)/2 in range. Instead use len(string)//2.  #exploit the fact that last index of string is -1. use 1 for loop for front traverse and one for back.
 #the default output of a function is true or false, no need to type print statements.
 
Day 0 (26/12): Making a plan. Writing down topics that would be covered.

#String: index blank = first element, index -1 = last element
         index must be an integer and we cannot use len(string)/2 in range. Instead use len(string)//2.
Problem 1704: my solution:

class Solution:
    def halvesAreAlike(self, s: str) -> bool:
        x=y=0
        l = len(s)
        for char in s[:l//2]:
            if char in "aeiouAEIOU":
                x +=1
        for char in s[l//2:]:
            if char in 'aeiouAEIOU':
                y+=1
        if x==y:
            return True
        else:
            return False
 
 better solution: 
 
 def halvesAreAlike(self, s: str) -> bool:
        v = set('aioeuAIOEU')
        i = 0
        a, b=0, 0
        for i in range(len(s)//2):
            if s[i] in v:
                a+=1
            if s[-i-1] in v:
                b+=1
        return a==b
 #exploit the fact that last index of string is -1. use 1 for loop for front traverse and one for back.
 #the default output of a function is true or false, no need to type print statements.
