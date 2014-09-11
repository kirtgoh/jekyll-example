---
layout: portfolio_entry
title: Reverse Words in a String
---

<pre>
source : https://oj.leetcode.com/problems/reverse-words-in-a-string/

My solution:

step - 1: skip whitespace

step - 2: get a word and reverse it using c++ standard library function

step - 3: get through all characters of string and append reversed word to a
new rs( reverse string).

{% highlight c %}
void Solution::reverseWords(string &s) 
{
    string rs; 
    for (int i = s.length() - 1; i >= 0; --i)                                                                                            
    {   
      // skip whitespaces
      while(i >= 0 && s[i] == ' ')
          --i;
      if (i < 0) break;

      // get a word, and reverse it
      string t;
      while(i >= 0 && s[i] != ' ')
        t.push_back(s[i--]);
      reverse(t.begin(), t.end());

      if (!rs.empty())
          rs.push_back(' ');
      rs.append(t);                                                                                                                                                                                                                    
    }   
    s = rs; 
}

{% endhighlight %}
</pre>
