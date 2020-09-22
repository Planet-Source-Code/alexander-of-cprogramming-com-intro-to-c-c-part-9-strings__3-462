<div align="center">

## Intro to C/C\+\+ Part 9: Strings


</div>

### Description

This lesson is one on strings. Strings are really arrays, but there are some different functions that are used for strings, like adding to strings, finding the length of strings, and also of checking to see if strings match. Strings are basically sentences, or words. Like, "This is a string".
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Alexander of CProgramming\.com](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/alexander-of-cprogramming-com.md)
**Level**          |Intermediate
**User Rating**    |4.6 (23 globes from 5 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Data Structures](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/data-structures__3-8.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/alexander-of-cprogramming-com-intro-to-c-c-part-9-strings__3-462/archive/master.zip)





### Source Code

<p><font face="Verdana">Strings are basically character arrays. For example, to
declare a string of 50 letters, you would want to say:</font></p>
<p><font face="Verdana">char string[50];</font></p>
<p><font face="Verdana">&nbsp;&nbsp;&nbsp;&nbsp; This would declare a string
with a length of 50 characters. Don't forget that arrays begin at 0, not 1 for
the index-number. Also, a string ends with a null character, literally a '/0'&nbsp;
character. But, just remember that there will be an extra character on the end
on a string. It is like a period at the end of a sentence, it is not counted as
a letter, but it still takes up a space.</font></p>
<p><font face="Verdana">&nbsp;&nbsp;&nbsp;&nbsp; What are strings useful for?
Well, for one thing, you might want to get a person's name. If you wanted to,
you would need a string, because a name can't fit in one variable! It is,
however, a collection of characters, and so fits nicely into a character array.&nbsp;</font></p>
<p><font face="Verdana">&nbsp;&nbsp;&nbsp;&nbsp; Now, what if you want to input
a string? Well, if you try to use cin&gt;&gt; then it won't work! It terminates
at the first space. However, you can use the function gets(char *s);.&nbsp; Gets
is basically a function that reads in a string and stops reading at the first
new-line, for&nbsp;example, when a user hits enter. Gets is in stdio.h. All you
do, is put the name of the array and it will work out, because the pointer char
*s is basically one way you tell a function that you will be passing an array,
although it is a pointer, it is still the string you give. Essentially, char *s
points to a string, and you can access this string just like an array.&nbsp; I
will touch upon this relationship as described above in another lesson that will
be a more advanced lesson on pointers and arrays.</font></p>
<p><font face="Verdana">&nbsp;&nbsp;&nbsp;&nbsp; Anyway, to get a string from a
user you want to use gets. An example program of this would be:</font></p>
<p><font face="Verdana">#include &lt;stdio.h&gt; //For gets<br>
#include &lt;iostream.h&gt; //For all other input/output functions</font></p>
<p><font face="Verdana">void main()</font></p>
<p><font face="Verdana">{</font></p>
<p><font face="Verdana">char astring[50]; //This declares a character array that
can be used as a string<br>
cout&lt;&lt;&quot;Please enter a string&quot;; //You should know this one!<br>
gets(astring); //The user will input a string(with spaces)<br>
cout&lt;&lt;&quot;You input: &quot;&lt;&lt;endl; //You know this one too!<br>
cout&lt;&lt;astring; //This is how you output character arrays, but not others!<br>
}</font></p>
<p><font face="Verdana">Ok, thats pretty simple. But, what if you want to use
some of the nifty functions from string.h?&nbsp; Well, these include the
following functions:</font></p>
<p><font face="Verdana">int strcmp(const char *s1, const char *s2);</font></p>
<p><font face="Verdana">strcmp will accept two strings. It will return an
integer. This integer will either be:<br>
<br>
Negative if s1 is less than s2.<br>
Zero if s1 and s2 are equal.<br>
Positive if s1 is greater than s2.</font></p>
<p><font face="Verdana">Strcmp is case sensitive.</font></p>
<p><font face="Verdana">int strcmpi(const char *s1, const char *s2);</font></p>
<p><font face="Verdana">strcmp will accept two strings. It will return an
integer. This integer will either be:</font></p>
<p><font face="Verdana">Negative if s1 is less than s2.<br>
Zero if the s1 and s2 are equal.<br>
Positive if s1 is greater than s2.</font></p>
<p><font face="Verdana">Strcmpi is not case sensitive, if the words are
capitalized it doesn't matter.</font></p>
<p><font face="Verdana">char *strcat(char *desc, char *src);</font></p>
<p><font face="Verdana">strcat is short for string cacatenate, which means to
add to the end, or append. It does just this, the first string is what the
second string is stuck on the end of. It basically returns the cacatenated
string. The first string will also have the entire string added to it.</font></p>
<p><font face="Verdana">char *strupr(char *s);</font></p>
<p><font face="Verdana">strupr converts a string to uppercase. It also returns a
string, which will all be in uppercase.&nbsp; The input string, if it is an
array, will also all be uppercase.</font></p>
<p><font face="Verdana">char *strlwr(char *s);</font></p>
<p><font face="Verdana">strlwr converts a string to lowercase. It also returns a
string, which will all be in uppercase.&nbsp; The input string, if it is an
array, will also all be uppercase.</font></p>
<p><font face="Verdana">size_t strlen(const char *s);</font></p>
<p><font face="Verdana">strlen will return the length of a string, minus the
termating character(/0). The size_t is nothing to worry about. Just treat it as
an integer.&nbsp; Some of the stuff in the strings may be confusing. The const
char *s stuff, for example. But, just remember that basically all of that will
be a string! It doesn't matter what the code is right now, just what the
functions do.&nbsp; Now, a small program using many of the string functions!</font></p>
<p><font face="Verdana">#include &lt;iostream.h&gt; //For cout</font></p>
<p><font face="Verdana">#include &lt;string.h&gt; //For many of the string
functions</font></p>
<p><font face="Verdana">#include &lt;stdio.h&gt; //For gets</font></p>
<p><font face="Verdana">void main()</font></p>
<p><font face="Verdana">{</font></p>
<p><font face="Verdana">char name[50]; //Declare variables</font></p>
<p><font face="Verdana">char lastname[50]; //This could have been declared on
the last line...</font></p>
<p><font face="Verdana">cout&lt;&lt;&quot;Please enter your name: &quot;; //Tell
the user what to do</font></p>
<p><font face="Verdana">gets(name); //Use gets to input strings with spaces or
just to get strings after the user presses enter</font></p>
<p><font face="Verdana">if(!strcmpi(&quot;Alexander&quot;, name)) //The ! means
not, strcmpi returns 0 for equal strings</font></p>
<p><font face="Verdana">{ //strcmpi is not case sensitive</font></p>
<p><font face="Verdana">cout&lt;&lt;&quot;That's my name too.&quot;&lt;&lt;endl;
//Tell the user if its my name</font></p>
<p><font face="Verdana">}</font></p>
<p><font face="Verdana">else //else is used to keep it from always outputting
cout&lt;&lt;&quot;That's not my name.&quot;</font></p>
<p><font face="Verdana">{</font></p>
<p><font face="Verdana">cout&lt;&lt;&quot;That's not my name.&quot;&lt;&lt;endl;</font></p>
<p><font face="Verdana">}</font></p>
<p>&nbsp;</p>
<p><font face="Verdana">cout&lt;&lt;&quot;What is your name in
uppercase...&quot;&lt;&lt;endl;</font></p>
<p><font face="Verdana">strupr(name); //strupr converts the string to uppercase</font></p>
<p><font face="Verdana">cout&lt;&lt;name&lt;&lt;endl;</font></p>
<p><font face="Verdana">cout&lt;&lt;&quot;And, your name in
lowercase...&quot;&lt;&lt;endl;</font></p>
<p><font face="Verdana">strlwr(name); //strlwr converts the string to lowercase</font></p>
<p><font face="Verdana">cout&lt;&lt;name&lt;&lt;endl;</font></p>
<p><font face="Verdana">cout&lt;&lt;&quot;Your name is
&quot;&lt;&lt;strlen(name)&lt;&lt;&quot; letters long&quot;&lt;&lt;endl;
//strlen returns the length of the string</font></p>
<p><font face="Verdana">cout&lt;&lt;&quot;Enter your last name:&quot;;</font></p>
<p><font face="Verdana">gets(lastname); //lastname is also a string</font></p>
<p><font face="Verdana">strcat(name, &quot; &quot;); //We want to space the two
names apart</font></p>
<p><font face="Verdana">strcat(name, lastname); //Now we put them together,we a
space in the middle</font></p>
<p><font face="Verdana">cout&lt;&lt;&quot;Your full name is &quot;&lt;&lt;name;
//Outputting it all...</font></p>
<p><font face="Verdana">}</font></p>

