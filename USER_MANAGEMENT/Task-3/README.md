# TASK: Your company needs a special user for a CI/CD system.

### Requirements:

Create a user named ciuser

1. UID must be 1700 

2. Primary group: ci (create if it doesn’t exist)

3. Secondary groups: docker, developers (create if they don’t exist)

4. Home directory: /srv/ciuser 

5. Login shell: /bin/bash 

6. Password: C1user@2025 

7. Force password to expire in 10 days

8. Prevent the user from changing the password before 3 days 

9. Lock the account immediately after creation 


# Answer

1. Add the groups

```
groupadd ci
groupadd docker
groupadd developers
```
2. Add the user
```
useradd -u 1700 -g ci -G docker,developers -m -d /srv/ciuser -s /bin/bash ciuser
```
Note: This satisfy the following

userid: 1700

primary group: -g ci

secondary group: -G docker,developers

create home directory: -m flag

set the home dir location: -d /srv/ciuser

set the shell: -s /bin/bash


3. Set the password

```
passwd ciuser
```

4. Force password to expire in 10 days

```
chage -M 10 ciuser

```

5. Prevent the user from changing the password before 3 days

```
chage -m 3 ciuser
```

6. Lock the account immediately after creation

```
passwd -l ciuser
```

### End of Task