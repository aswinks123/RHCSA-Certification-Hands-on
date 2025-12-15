# TASK: YThe company wants a temporary developer account for testing purposes.

### Requirements:

1. Create a user named tempdev 

2. UID: 1900 

3. Use a skeleton directory /etc/skel_dev for the home directory contents 

4. Home directory: /opt/tempdev 

5. Account should expire automatically after 7 days

6. Force password change at first login

# Answer

1. Create a skell directory if it doesn't exist:

```
mkdir /etc/skel_dev
```

2. Create a user named: tempdev with following attribute

```
useradd -u 1900 -k  /etc/skel_dev -m -d /opt/tempdev   tempdev

```

Following are satisfied:

user tempdev created

UUID set to 1900

home directory set to : /opt/tempdev

used the skell diretory : /etc/skel_dev for creating the home directory

3. Account should expire automatically after 7 days

```
chage -E 2025-12-21 tempdev
```

4. Force password change at first login

```
chage -M -1 tempdev
```
