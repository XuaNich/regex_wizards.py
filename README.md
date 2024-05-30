#!/usr/bin/env python
# coding: utf-8

# In[1]:
# will try improving this at a later date


from tests import tests


# ## Search Function

# In[2]:


import re

# Search for the string "cat" in the text "The cat in the hat"
text = "The cat in the hat."
x = re.search("cat", text)
print(x) # Output: <re.Match object; span=(4, 7), match='cat'>


# In[4]:


tests.ch2()


# ## Advanced Search Function 1/2
# 

# In[6]:


import re

#Search for any three characters in the text "The cat in the hat"
text = "The cat in the hat"
x = re.search("cat", text)
print(x) # Output: <re.Match object; span=(4, 7), match='cat'>


# In[7]:


tests.ch3()


# ## Advanced Search Function 2/2

# In[8]:


import re

# Search for a digit in the text "The cost is $5."
text = "The cost is $5."
x = re.search("\d", text)
print(x) # Output: <re.Match object; span=(13, 14), match='5'>


# In[9]:


tests.ch4()


# ## Group Function 1/2

# In[10]:


import re

# Search for a vowel in the text "The cat in the hat"
text = "The cat in the hat"
x = re.search("[aeiou]", text)
print(x.group()) # Output: e


# In[11]:


tests.ch5()


# ## Group Function 2/2

# In[14]:


import re

# Matching a phone number
phone_number = "123-456-7890"
phone_regex = r'^\d{3}-\d{3}-\d{4}$'
x = re.search(phone_regex, phone_number)
print(x.group()) # Output: 123-456-7890


# In[15]:


tests.ch6()


# ## SPLIT Method

# In[16]:


import re

text = "The cat is cute. The dog is also cute."
x = re.split("\.", text)
print(x) # Output: ['The cat is cute', ' The dog is also cute', '']


# In[17]:


tests.ch7()


# ## Findall Method

# In[18]:


import re

text = "The cat is cute. The dog is also cute."
x = re.findall("cute", text)
print(x) # Output: ['cute', 'cute']


# In[19]:


tests.ch8()


# ## Finditer

# In[22]:


import re

text = "The cat is cute. The dog is ugly."

x = re.finditer("(cat|dog) is (cute|ugly)", text)
for match in x:
  print(match.group(), end=' ')  # Output: cat is cute dog is ugly 


# In[23]:


tests.ch9()
