**Authorization** --> What a user can do???

Defining what you are allowed to do as a valid user in the platform.

**RBAC (Role Based Access Control)**
Very widely used authorization model, used for managing usr permission

**![[25.png]]**

Here the person 2 is has two different roles so it can access the data/services accessible by both role 1 and role 2.

**How do you implement RBAC ??**

DB table with following

**ROLES AND PERMISSIONS HAVE MANY TO MANY RELATIONSHIP**

| Role Table                                                 | Permission Table                 | role_permission                               | user_roles                                                |
| ---------------------------------------------------------- | -------------------------------- | --------------------------------------------- | --------------------------------------------------------- |
| -id<br>-name<br>-description<br>-created_at<br>-updated_at | -id<br>-name<br>-description<br> | -id<br>-role_id<br>-created_at<br>-updated_at | -id<br>-user_id<br>-role_id<br>-created_at<br>-updated_at |
