# TASK: A new employee joins the company. Create the user based on the requirements.

### Requirements:


1. Create a user named alex - ok

2. User ID must be 1500 - ok 

3. Primary group must be staff - ok

4. Home directory must be /home/alex - ok

5. Login shell must be /bin/bash -ok

6. Set the password to RedHat@1500

7. Force the user to change password at first login


### ANSWERS

1. Create a user named alex:

This will create a user alex with all the requirement expect "Force the user to change password at first login"

```
useradd -u 1500 -g staff -m -d /home/alex -s /bin/bash alex
```

2. Set the Password:

```
passwd alex

<Enter the password as: RedHat@1500 >

```


3. Force user to change password at first login:

```
chage -d 0 alex
```


## Learning:

To maually set the userID : -u <user-ID>

To create home directory for user: -m flag

To specify the home directory location: -d <path of home>

To specify the shell: -s <path to shell>


To force password change: chage -d <number og days to expire> <username>
```
chage -d 0 <user name> : This will force user to chnage password on next login

chage -d -1 <user name> : This will set the password to never expire
```

To force a user to chnage the password after 5 days.

```
chage -M 5 <user name> : Force to change password after 5 days . Notice the -M flag
```

To prevent a user from chnaging the password before 2 days

```
chage -m 2 <user name> : This prevent the user from chnaging his password before 2 days.
```
