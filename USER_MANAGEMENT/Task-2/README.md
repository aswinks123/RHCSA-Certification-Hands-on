# TASK: A user "tempuser" has left the company temporarily, but you don’t want to delete their account.

### Requirements:

1. Lock the user account so they cannot log in

2. Ensure all their files remain intact

3. Later, unlock the account so they can log in again




### Answer

 To lock a user account   

 ```
 passwd -l tempuser
 ``` 

To unlock the user account

```
passwd -u tempuser
```


### End of Task