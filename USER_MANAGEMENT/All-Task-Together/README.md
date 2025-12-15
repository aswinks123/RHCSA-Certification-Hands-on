# This is the maximum use case questions RHCSA can ask.


### 1. User Creation

```
Create a user devtest

UID: 1950

Primary group: developers

Secondary groups: docker, ci

Home directory: /opt/devtest

Skeleton directory: /etc/skel_dev

Login shell: /bin/bash
```

### 2. Password Management
```
Set password: RHCSA@2025

Force password change at first login

Password expires every 10 days

Prevent password change before 3 days

Warn 2 days before password expires
```
### 3. Account Expiry
```
Account expires after 14 days

Set inactive days after password expiry (e.g., 2 days)
```
### 4. Account Lock/Unlock
```
Lock account immediately after creation

Unlock account when needed (usermod -U)
```

### 5. Optional Extras 
```
Modify user secondary groups after creation: usermod -aG <group>

Change login shell after creation: chsh -s /bin/zsh devtest

Delete the user and optionally remove home directory: userdel -r devtest

Set a user without a home directory for system accounts
```

# Lets complete this task

### 1. User Creation 

```
groupadd developers
groupadd docker
groupadd ci
mkdir -p /etc/skel_dev 


useradd -u 1950 -g developers -G docker,ci -m -d /opt/devtest -k /etc/skel_dev -s /bin/bash  devtest


```

Following are satisfied:

Create a user devtest

UID: 1950

Primary group: developers

Secondary groups: docker, ci

Home directory: /opt/devtest

Skeleton directory: /etc/skel_dev

Login shell: /bin/bash


