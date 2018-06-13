Assignment1:
●Setup unix based authentication
●Configure Matrix based authorization.
.
Solution : Enable unix based authentication  Goto Manage Jenkin -> Global configuration security -> Security Realm (Unix user and group database)



●Implement project based matrix based authorization.
Solution : 

Using “Jenkins’ own user database”. Select this radio button under “Security Realm”.
Under Authorization, select “Project-based Matrix Authorization Strategy” and add two users, one administrator (say admin) and a regular user (say user1)
●Setup a role based user authentication and authorization.
Solution : Install Role-based Authorization Strategy plugin jenkin.
After  created two roles Agent and job in the Manage role. Assign this roles to user.



Assignment3:
●Add a slave to your jenkins, restrict some of the job to your slave.
Solution : Goto 
Manage jenkin -> manage node
