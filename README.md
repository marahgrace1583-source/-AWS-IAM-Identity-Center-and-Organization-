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
 ![image alt](https://github.com/marahgrace1583-source/-AWS-IAM-Identity-Center-and-Organization-/blob/9bef9ada7d6d003f0326c9928c0f1d736f22c58b/2025-07-11.png)      
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

![WhatsApp Image 2025-07-10 at 9.12.36 AM.jpeg](attachment:8f222712-0627-4d3b-9df2-0652cce0f655:80e4f4e0-1259-4077-961f-4225d2a55ae2.png)

<aside>
💡

*We encountered an issue here. The reasons were because AWS has a default limit of 2 accounts but you can request 8 more accounts by using a service called quota, but people in Nigeria are not eligible, we contacted support to see if the issue can be resolved but we are still waiting for responses*

![WhatsApp Image 2025-07-10 at 10.24.04 PM.jpeg](attachment:9c98d5d3-3d85-4534-812e-dcf214abbf68:WhatsApp_Image_2025-07-10_at_10.24.04_PM.jpeg)

</aside>

![WhatsApp Image 2025-07-10 at 9.12.37 AM.jpeg](attachment:fb702810-9115-4ef3-a0aa-20ead5b6056d:876b34ee-b658-405e-afc4-1fd1179b971e.png)

![WhatsApp Image 2025-07-10 at 9.12.38 AM.jpeg](attachment:cfc532f4-d09a-461e-ba87-f6f1586fd036:b2785016-bec6-4e7f-a6c0-ece3026266e4.png)

### **Step 2:**

<aside>
💡

**Use AWS IDENTITY CENTER to create 5 users**

</aside>

Go to ***Root Account*** first, **enable it**, and:

- Click on IAM identity center
- Create five (5) users
- Add the users to the group

![WhatsApp Image 2025-07-10 at 9.12.38 AM (1).jpeg](attachment:f73a1007-1612-49fb-be52-6147309d2861:b5fa5692-b528-4488-b624-96d13d93c9ef.png)

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

![WhatsApp Image 2025-07-10 at 9.12.38 AM (2).jpeg](attachment:7a519931-f91b-4f4c-907b-8df4bc411d1f:36a6c348-2202-4d6d-a925-3ad0696165c6.png)

![WhatsApp Image 2025-07-10 at 9.12.36 AM (1).jpeg](attachment:f77f0d79-671b-4d18-a7d0-60aa6ed04ffd:f6f4cf36-c6ff-47a8-b0a4-8d4631bfc066.png)

### Step 4:

<aside>
💡

Assign permission to each groups using *Permissions Set Policy* 

</aside>

- Click on *“Group”* and assign *permission set* to all users.

![WhatsApp Image 2025-07-10 at 9.12.39 AM (1).jpeg](attachment:ed66ea4a-8013-49d0-8237-b627f6a13d16:07936e6f-f114-44ff-813b-e4dc7d5bb3ee.png)

![WhatsApp Image 2025-07-10 at 9.12.39 AM.jpeg](attachment:1eec2e54-cdf6-4c61-a88d-2fcc6e378494:0d894dfd-96c9-4ff7-b69a-b172fc8c9fc9.png)

### Step 5:

<aside>
💡

All users logged into their account using MFA *(Screenshots below)*

</aside>

![WhatsApp Image 2025-07-10 at 4.19.38 PM (1).jpeg](attachment:74620a09-e3bb-46b6-8bab-e1608cb8664f:072ac0f8-1572-497d-b53f-e3d7b03fa7d6.png)

![WhatsApp Image 2025-07-10 at 4.15.36 PM (1).jpeg](attachment:d43274e4-d708-43c7-bc7d-675c8f90e9e4:WhatsApp_Image_2025-07-10_at_4.15.36_PM_(1).jpeg)

![WhatsApp Image 2025-07-10 at 10.09.43 PM.jpeg](attachment:77ec6337-20f8-4057-a171-448c73df1ff7:WhatsApp_Image_2025-07-10_at_10.09.43_PM.jpeg)

![WhatsApp Image 2025-07-10 at 10.09.43 PM (1).jpeg](attachment:5bf7fd48-a05e-4430-b8f8-d361f5183759:WhatsApp_Image_2025-07-10_at_10.09.43_PM_(1).jpeg)

![WhatsApp Image 2025-07-10 at 10.09.43 PM (2).jpeg](attachment:22528d96-5e9e-4b65-b289-e00e9b58cfca:WhatsApp_Image_2025-07-10_at_10.09.43_PM_(2).jpeg)

![WhatsApp Image 2025-07-10 at 10.04.29 PM.jpeg](attachment:e7689ab0-3969-4cb2-97b5-bc3e3c5cfcb3:1a79de73-eb5e-4004-927e-04feff8e78f6.png)

![WhatsApp Image 2025-07-10 at 10.04.29 PM (1).jpeg](attachment:5dce5b27-8ff9-43fb-9b60-1aad46ad07a5:ccc196c6-953b-4333-96e6-5fa7972e699d.png)

![WhatsApp Image 2025-07-10 at 10.04.29 PM (2).jpeg](attachment:7469d8f4-255e-4a55-afbe-fab2bdc62747:2eb8f516-afa4-4bdf-8d32-2eaff2a06307.png)

![WhatsApp Image 2025-07-11 at 9.02.24 AM.jpeg](attachment:baf8f900-fd57-4479-99f2-5bbb91880fc7:WhatsApp_Image_2025-07-11_at_9.02.24_AM.jpeg)

![WhatsApp Image 2025-07-11 at 9.02.24 AM (1).jpeg](attachment:3f846428-e451-45c4-89ce-b1ddb01575eb:WhatsApp_Image_2025-07-11_at_9.02.24_AM_(1).jpeg)

![WhatsApp Image 2025-07-11 at 9.02.25 AM.jpeg](attachment:721bed28-b079-471b-93b4-7df52226c7d6:WhatsApp_Image_2025-07-11_at_9.02.25_AM.jpeg)

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

![WhatsApp Image 2025-07-10 at 9.12.39 AM (2).jpeg](attachment:fc31f151-d474-4326-9cb9-73f4014b39f7:25076291-afd1-49bd-a1eb-40a73d8b6650.png)

### **Step 7:**

<aside>
💡

Each user account captures the first authentication and MFA token and shows how you switch to another account. From AWS account portal, click account from administrative access link it takes us to console home 

</aside>

![WhatsApp Image 2025-07-10 at 9.12.38 AM (3).jpeg](attachment:3130f62f-2ea3-4a8f-80da-0bc64f1ee1e6:455d7734-9bc2-48e2-9ca0-c9b1a680e6f5.png)

![WhatsApp Image 2025-07-10 at 9.12.39 AM (3).jpeg](attachment:3e61073f-578e-4c12-8834-e57aae3e9118:605109c2-e348-41f4-aadd-e4381cdfc6c5.png)
