
# coding: utf-8

# In[1]:


import pandas as pd
import numpy as np


# In[2]:


telecom = pd.read_csv("C:/Users/LENOVO/Desktop/Simplilearn/dataset/Comcast_telecom_complaints_data.csv")


# In[7]:


telecom



#  # Provide the trend chart for the number of complaints at monthly and daily granularity levels.
#  

# In[47]:


import matplotlib.pyplot as plt
get_ipython().magic('matplotlib inline')
import seaborn as sns


# In[5]:


telecom['Date'] = pd.to_datetime(telecom['Date'])


# In[180]:


comp_by_date = telecom.groupby(['Date']).size()
new_df = comp_by_date.to_frame(name = 'no_of-comp_each_day').reset_index()

new_df


# In[173]:


plt.plot(comp_by_date)
plt.xticks(rotation = 90)
plt.show()


# 
# 
# # Provide a table with the frequency of complaint types.

# In[41]:


telecom = pd.DataFrame(telecom)


# In[175]:


freq_comp = telecom.groupby("Customer Complaint")['Customer Complaint'].count()
freq_comp


# In[176]:


types_comp = pd.DataFrame(freq_comp)
types_comp


# In[67]:





# ### Which complaint types are maximum i.e., around internet, network issues, or across any other domains.

# In[68]:


print(types_comp.max())


# ### Create a new categorical variable with value as Open and Closed. Open & Pending is to be categorized as Open and Closed & Solved is to be categorized as Closed.

# In[177]:


telecom['final_status'] = telecom['Status']


# In[178]:


telecom['final_status'] = telecom['final_status'].replace(to_replace = ["Solved"], value = "Closed")
telecom['final_status'] = telecom['final_status'].replace(to_replace = ["Pending"], value = "Open")
telecom.head(10)


#  ### Provide state wise status of complaints in a stacked bar chart. Use the categorized variable from Q3. Provide insights on:

# In[67]:


df = telecom.groupby(['State','final_status'])['State'].count().unstack('final_status').fillna(0)
df.plot(kind = "bar", stacked = True)
plt.show()



# ### Which state has the maximum complaints

# In[96]:


max_state = telecom.groupby('State').size()
new_df = max_state.to_frame(name = 'size').reset_index()
new_df.max()


# ### Which state has the highest percentage of unresolved complaints
# 

# In[148]:


max_state = telecom.groupby(['State','final_status']).size()
new_df = max_state.to_frame(name = 'size').reset_index()
new_df =  new_df[new_df['final_status']== "Open"]
total_pending = new_df['size'].sum()








# In[156]:


percent = []

for i in a:
    per = i/total_pending*100
    percent.append(per)
    
   
new_df['percent'] = percent

new_df.max()


# ### Provide the percentage of complaints resolved till date, which were received through the Internet and customer care calls.
# 
# 

# In[169]:


total_comp = telecom1.groupby(['Received Via','final_status']).size()
new_df = total_comp.to_frame(name = 'size').reset_index()
new_df
new_df = new_df[new_df['final_status'] == "Closed"]
total_solved_queries = new_df['size'].sum()
total_solved_queries


# In[171]:


percent = []

for i in new_df['size']:
    per = i/total_solved_queries*100
    percent.append(per)
    
   
new_df['percent'] = percent

new_df


# In[ ]:


new_df['combo'] = new_df['State'].map(str) + '(' + new_df['size'].map(str) +')'   # it combine columns 
new_df['combo'].astype(str).groupby(new_df['State']).agg(['size',', '.join])
new_df['combo'].m


# In[113]:


telecom1.head(15)


# In[30]:


telecom1 = telecom
telecom1['new_col'] = telecom1['Status']


# In[36]:


telecom1['new_col'] = telecom1['new_col'].replace(to_replace = ["Solved"], value = "Closed")
telecom1['new_col'] = telecom1['new_col'].replace(to_replace = ["Pending"], value = "Open")
telecom1.head(10)


# 
# 
# 
#          
#     
#             
#     
#         

# In[37]:



         
                


# In[24]:


telecom1.head()


# In[ ]:


telecom1['new_col'] = "Open"
   elif i == "Solved":
       telecom1['new_col'] = "Closed"
   elif i == "Closed":
        telecom1['new_col'] = "Closed"
   elif i == "Open":
       telecom1['new_col'] = "Open"
              
              
             


# In[87]:


telecom['final_status' == "Pending"] = "Open"
telecom['final_status' == "Solved"] ="Closed"


# In[88]:





# In[89]:



telecom.tail(10)

