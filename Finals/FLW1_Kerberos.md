![image](https://github.com/user-attachments/assets/c07ac72b-55c0-45d2-a495-cef540868fb0)


# SYSADM1 -- Kerberos Lab Activity: A step-by-step Guide

**Objective:**

Set up a basic Kerberos authentication system to understand how Kerberos
manages secure logins through ticket-based access.

**Setup Requirements:**

-   Two VMs in Oracle VM, both running a Linux distribution like Ubuntu
    or CentOS.

-   VM1: Kerberos Server

-   VM2: Kerberos Client

**Step 1: Initial Setup and Package Installation**

1.  **Update Packages on Both VMs:**

    -   Open a terminal on each VM and run:

*bash*

*sudo apt update && sudo apt upgrade --y*

![image](https://github.com/user-attachments/assets/93462315-479f-4a87-98be-22b7e87dd000)


2.  **Install Kerberos Server Packages on VM1 (Kerberos Server):**

    -   In VM1, install the Kerberos Key Distribution Center (KDC) and
        admin server:

*bash*

*sudo apt install krb5-kdc krb5-admin-server --y*

![image](https://github.com/user-attachments/assets/cacc8e17-bb7c-4813-82b8-fb6fc44ccbbd)


3.  **Install Kerberos Client Package on VM2 (Kerberos Client):**

    -   In VM2, install the Kerberos client software:

*bash*

*sudo apt install krb5-user -y*

-   During installation, when prompted, enter the Kerberos realm you
    plan to set up, e.g., MYLAB.LOCAL.

![image](https://github.com/user-attachments/assets/f1b0f5c6-c332-4e9a-afc4-e9c599c8cd3f)


**Step 2: Configure the Kerberos Server (VM1)**

1.  **Edit the Kerberos Configuration File:**

    -   Open /etc/krb5.conf for editing:

*bash*

*sudo nano /etc/krb5.conf*

-   Set the realm as MYLAB.LOCAL. You should also specify the KDC and
    admin server as VM1's hostname or IP address:

ini

\[libdefaults\]

default_realm = MYLAB.LOCAL

\[realms\]

MYLAB.LOCAL = {

kdc = \<VM1_IP_or_hostname\>

admin_server = \<VM1_IP_or_hostname\>

}

-   Save and close the file (Ctrl+X, then Y, and Enter to confirm).

![image](https://github.com/user-attachments/assets/f74f9940-9589-433b-9662-d6ce5150ae5e)


2.  **Initialize the Kerberos Database:**

    -   Create the database for the Kerberos realm:

*bash*

*sudo krb5_newrealm*

-   You will be prompted to set a password for the Kerberos database.

![image](https://github.com/user-attachments/assets/0fb237b3-dbd0-4bc8-97c0-d6966445b024)


3.  **Start and Enable the Kerberos Services:**

    -   Start the KDC and admin server, and ensure they start
        automatically on boot:

*bash*

*sudo systemctl start krb5-kdc*

*sudo systemctl start krb5-admin-server*

*sudo systemctl enable krb5-kdc*

*sudo systemctl enable krb5-admin-server*

![image](https://github.com/user-attachments/assets/34b27f89-6e40-4658-b4c5-698fa8188352)


**Step 3: Set Up a Kerberos User Principalsud**

1.  **Create a New User Principal:**

    -   Run the following command to create a test user in the Kerberos
        realm:

*bash*

*sudo kadmin.local -q \"addprinc testuser@MYLAB.LOCAL\"*

-   Set a password for testuser.

![image](https://github.com/user-attachments/assets/ebc31a0c-888d-4ee5-9303-d00632e51d45)


2.  **Verify the User Principal:**

    -   To confirm the principal is created, list all principals:

*bash*

*sudo kadmin.local -q \"listprincs\"*

![image](https://github.com/user-attachments/assets/6b7bec7e-893e-49b4-b098-e474a87cdc3b)


**Step 4: Configure the Kerberos Client (VM2)**

1.  **Edit the Kerberos Configuration File on VM2:**

    -   Open /etc/krb5.conf for editing on VM2:

*bash*

*sudo nano /etc/krb5.conf*

-   Set the default realm to MYLAB.LOCAL and point to the KDC and admin
    server on VM1. The configuration should match what you set on VM1.

![image](https://github.com/user-attachments/assets/57fa9909-15c1-445f-a9f5-174f35c12929)


**Step 5: Test Kerberos Authentication**

1.  **Request a Kerberos Ticket for the User on VM2:**

    -   In the terminal on VM2, request a ticket for testuser:

*bash*

*kinit testuser@MYLAB.LOCAL*

-   Enter the password you set for testuser.

![image](https://github.com/user-attachments/assets/be33838d-a236-4d4d-86a0-ef139d857692)


2.  **Verify the Ticket:**

    -   Check if the ticket was issued by listing active Kerberos
        tickets:

*bash*

*klist*

-   You should see details about the ticket, such as the principal and
    expiration time, confirming successful Kerberos authentication.

![image](https://github.com/user-attachments/assets/6b00361d-1fbd-43c7-a48a-2509957c1773)

