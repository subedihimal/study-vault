**Authorization** --> What a user can do???

Defining what you are allowed to do as a valid user in the platform.

**RBAC (Role Based Access Control)**
Very widely used authorization model, used for managing usr permission

**![[25.png]]**

Here the person 2 is has two different roles so it can access the data/services accessible by both role 1 and role 2.

### **How do you implement RBAC ??**

**DB table with following**

**ROLES AND PERMISSIONS HAVE MANY TO MANY RELATIONSHIP**

| Role Table                                                 | Permission Table                                         | role_permission                               | user_roles                                                |
| ---------------------------------------------------------- | -------------------------------------------------------- | --------------------------------------------- | --------------------------------------------------------- |
| -id<br>-name<br>-description<br>-created_at<br>-updated_at | -id<br>-name<br>-description<br>-resource<br>-action<br> | -id<br>-role_id<br>-created_at<br>-updated_at | -id<br>-user_id<br>-role_id<br>-created_at<br>-updated_at |
**Here** 
Permission table can have data like -> 
1, user_read, "is able read data", "user", "read"
2, user_write, "is able to create and update", "user", "create and update"
...

### Another way of implementing RBAC

**Hierarchical RBAC**
![[26.png]]


If you give a user the role of parent all the child roles are accessible to that user. But you can also restrict a child role to them. Example if you give an admin role you can choose to restrict the video:delete role to that user.