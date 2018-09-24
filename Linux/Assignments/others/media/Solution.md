# Task
```
 There is a company which has multiple projects, and they are very strict about there daily sync-up meetings. 
 They have introduced a fine system where if a person/person(s) gets late in joining the meeting they have to treat everyone with a cup of coffee. 
 The contribution of people will vary depending on by how much time they were late. Please come with a solution for same.
```

# Solution

```
from datetime import timedelta
from datetime import datetime
from datetime import date
from datetime import time

print ("Welcome Opstree")
totEmp= int(input("Enter total number of the employee "))
cupCost = int(input("Enter the cost of coffee per cup "))
totCost= totEmp * cupCost
today= date.today()
fixTime = datetime(today.year, today.month, today.day, 10, 00, 00)
totaldelay = 0
employees = []
employInTime= []
employDelayTime=[]


for x in range(0,totEmp):
    name=str(input("Enter employee " + str(int(x+1)) +" name "))
    time= datetime.now()
    ptime= time.strftime("%X")
    employees.insert(x, name)
    print("System Generated current time for employee " + str(employees[x]) + " : " + str(ptime))
    employInTime.insert(x, time)
    delaytime= employInTime[x]-fixTime
    delaySeconds= delaytime.seconds
    delayMinutes= int(delaySeconds/60)     
    employDelayTime.insert(x, delayMinutes)

for x in range(len(employDelayTime)):
    totaldelay= totaldelay + employDelayTime[x]
factor= totCost/totaldelay
    
for x in range(len(employDelayTime)):
  if employDelayTime[x] != 0:
    cost= int(int(employDelayTime[x])*factor)
    print(str(employees[x]) + " Contribution " + str(cost))
    
```

![Link to image](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/others/media/try.png "Image")
       


