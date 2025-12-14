# TASK: A new employee joins the company. Create the user based on the requirements.

### Requirements:


1. Create a user named alex

2. User ID must be 1500 

3. Primary group must be staff 

4. Home directory must be /home/alex 

5. Login shell must be /bin/bash

6. Set the password to RedHat@1500

7. Force the user to change password at first login


### ANSWERS

1. Create a user named alex with the required settings

This will create a user alex with all the requirement expect "Force the user to change password at first login"

```
useradd -u 1500 -g staff -m -d /home/alex -s /bin/bash alex
```

Note: If staff group is not already available create one using the command:  groupadd staff

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

To maually set the userID : -u 

To create home directory for user: -m

To specify the home directory location: -d path of home

To specify the shell: -s path to shell


To force immidiate password change:

```
chage -d 0 <user name> : This will force user to change password on next login

chage -d -1 <user name> : This will set the password to never expire
```

To force a user to change the password after 5 days.

```
chage -M 5 <user name> : Force to change password after 5 days . Notice the -M flag
```

To prevent a user from changing the password before 2 days

```
chage -m 2 <user name> : This prevent the user from changing his password before 2 days. This is to set min days for password change.
```

### End of Task