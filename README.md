Q12 : Search String
===================

**Question 12.** Find all strings “_**mbms**_” from “_**/usr/share/dict/words**_” file and copy that strings in a _**/root/lines**_ file.

**Answer**

```
# To find and copy just the string
grep -o mbms /usr/share/dict/words  > /root/lines

# Note: To find and copy all the line instead, you will use this:
grep mbms /usr/share/dict/words  > /root/lines
```
