# -AWS-IAM-Identity-Center-and-Organization-
This project establishes a structured AWS identity management system across three AWS accounts: Development, Staging, and Production, using AWS Identity Center for centralized, secure, role-based access control.
### **Project Scope Overview**

1. **AWS Organization Configuration:** Create an AWS Organization with a **management (root) account** overseeing **three member accounts**: **Dev**, **Staging**, and **Production** for centralized billing, security, and policy management.
    - Document challenges and troubleshooting steps during account setup.
    - Capture screenshots at each step.
2. **User and Group Management via AWS Identity Center:** Create **five users** in AWS Identity Center, grouped by roles:
    - **Admin-Team**: 1 user
    - **DevOps Team**: 2 users
    - **Developer Team**: 2 users
        
        These groups enforce role-based access policies for better security.
        
3. **Permission Sets Creation:** Define four permission sets:
    - **Admin-permission**
    - **PowerUser-permission**
    - **SystemAdmin-permission**
    - **DataScientist-permission**
        
        These control user actions within AWS.
      
4. **Role-Based Permission Assignments:** Map permissions to groups:
    - **Admin-Team** → Admin-permission
    - **DevOps Team** → PowerUser & SystemAdmin permissions
    - **Developer Team** → DataScientist permission
5. **MFA Implementation:** Implement **Multi-Factor Authentication** requiring password plus second factor for AWS access.
6. **Cross-Account Access:** Grant all users access to all accounts with **role-based permission controls** determining their access level in each account.
7. **SSO and Account Switching:** Validate user logins, document password/MFA setup, and demonstrate **account switching via AWS SSO**.
8. **Documentation:** Document all steps with screenshots and notes.

---

## Tools required

- AWS management console
- internet
- Basic AWS account

## Step-by-Step Illustration

### **Step 1:**

<aside>
💡

**Create an AWS organization** 

</aside>

- Go to the AWS org in the console
- Click Create Organization and select Enable features
- Wait for the organization to get created



<aside>
💡

*We encountered an issue here. The reasons were because AWS has a default limit of 2 accounts but you can request 8 more accounts by using a service called quota, but people in Nigeria are not eligible, we contacted support to see if the issue can be resolved but we are still waiting for responses*



</aside>




### **Step 2:**

<aside>
💡

**Use AWS IDENTITY CENTER to create 5 users**

</aside>

Go to ***Root Account*** first, **enable it**, and:

- Click on IAM identity center
- Create five (5) users
- Add the users to the group



- Create 3 groups based on roles:

<aside>
💡

- *Admin  <<<<<<< 1 user*
- *Devops <<<<<< 2 users*
- *Developers <<<< 3 users*
</aside>

       

![2025-07-09 (4).png](attachment:6aa6b4c2-9c78-497b-a72d-89b6248f2acb:957caf29-f4fa-4c13-993f-47ede8ab425f.png)

### Step 3:

<aside>
💡

Create and attach an IAM policy to manage permissions 

</aside>

- Click on *“Permission sets”*
- It will take you to *admin* permission
- Add description and set duration

<aside>
💡

*The same method used in creating admin permission is the same as power user, system admin, and data scientist* 

</aside>



### Step 4:

<aside>
💡

Assign permission to each groups using *Permissions Set Policy* 

</aside>

- Click on *“Group”* and assign *permission set* to all users.



### Step 5:

<aside>
💡

All users logged into their account using MFA *(Screenshots below)*

</aside>


### Step 6:

<aside>
💡

Allow users to have access to all accounts by only permission under multi-action permission for the Admin team 

</aside>

- Click on *“Assign users /group”*, check the box for the admin team
- Click on the *“AWS account”*, check the box of one of the accounts named **Kenneth Digital**
- Check the box for the admin team
- Click on next give it permission which is administrator access then
- Click *“Next”* and *“Submit”*

<aside>
💡

***For Developer***

</aside>

- Proceed to click on *“Assign users /group”*, check the box for the admin team
- Click on the *“AWS account”*, check the box of one of the accounts named **Kenneth Digital**
- Check the box for the development team
- Click on next check the box for data scientist
- Click *“Next”* and *“Submit”*

<aside>
💡

***For Devops***

</aside>

- under multi-action permission
- Click on the AWS account, check the box of one of the accounts named Kenneth digital.
- Then click on assign *“users/group”*
- Click on the ***“DevOps team”,*** Click on ***“Next”***
- Check the box for ***“power user access”*** and *“system administrator”*.
- Click *“Next”* and *“Submit”*



### **Step 7:**

<aside>
💡

Each user account captures the first authentication and MFA token and shows how you switch to another account. From AWS account portal, click account from administrative access link it takes us to console home 

</aside>


