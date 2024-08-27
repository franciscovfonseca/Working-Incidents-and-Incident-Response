<br>

<h1 align="center">Working Incidents & Incident Response</h1>

<br>

  <details close> 
  
**<summary> 📝 Context</summary>**

We'll now start practicing **Incident Response**.

We have accumulated a decent number of Incidents over the last 24 Hours:

<br>

![azure portal](https://github.com/user-attachments/assets/9c1cce53-082a-4c9e-b6d5-7da25a14a9d7)

<br>

So we’re going to take our time and work our way through some of these ➜ as if we’re working as a **SOC Analyst**.

Basically in this lab we’re going to practice the **NIST 800-61 Incident Management Lifecycle**.

In reality ➜ every Organization practices Incident Response a little differently than one another.

We won’t be using here the “absolute best way” to do Incident Response** ➜ but we’ll be adhering to the NIST 800-61 Lifecycle of:

-	**Preparation**
-	**Datection & Analysis**
-	**Containment, Eradication & Recovery**
-	**Post-Incident Activity**

<br>

<h2></h2>

  </details>

<br>


In this lab we're going to **Investigate & Work the Incidents** being generated within **Microsoft Sentinel**.

We'll do this in accordance with the [**NIST 800-61**](https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-61r2.pdf) **Incident Management Lifecycle**.

<br>

<p align="center">
<img width="700" src="https://github.com/user-attachments/assets/66745d60-fc59-406b-9955-b371304e4d98" alt="Banner"/>

<br>

<br>

<details close> 
<summary> <h2>Guidelines for Incident Response</h2> </summary>

<br>

### Step 1️⃣ ➜ Preparation

<br>

We've completed this step already by:

- Setting Up **Logging** for all of our Resources.

- **Ingesting all of the Logs** into the **Log Analytics Workspace**.

- Configuring **Microsoft Sentinel** & **Alert Rules**.

<br>

<h2></h2>

<br>

### Step 2️⃣ ➜ Detection & Analysis

<br>

>   <details close> 
>   
> **<summary> 📝 Explanation</summary>**
> 
> This phase gets kicked off when someone notices some kind of **Anomaly in the System**.
> 
> In our case we configured a bunch of Alerts ➜ and the fact that an **Incident was Created** ➜ is the beggining of our **Detection Phase**.
> 
>   </details>

<br>

|                   |                                  |
| ------------------------------ | ------------------------------------------ |
| 1              | Set the **Severity**, the **Status** & the **Owner** of the Incident. |
| 2                | **View Full Details**.                |
| 3     | Observe the **Activity Log** (for the History of the Incident).                    |
| 4  | Observe the **Entities** & **Incident Timeline**.                    |
| 5  | **Investigate the Incident** and continue trying to **Determine the Scope**.                   |
| 6  | **Inspect the Entities** and see if there are any **Related Events**.                   |
| 7  | **Determine Legitimacy** of the Incident.                    |
| 8  | If **True Positive** ➜ Continue | If **False Positive** ➜ Close it out.                   |

<br>

<h2></h2>

<br>

### Step 3️⃣ ➜ Containment, Eradication & Recovery

We'll use this simple [**Incident Response PlayBook**](https://docs.google.com/document/d/1EQ5MzN95POLaRIMulYg3PIH3UGHtDNcGdkFvgOXyEXQ/edit#heading=h.uyxi3urvol4g) to **Remediate the Incidents**.

<br>

>   <details close> 
>   
> **<summary> 💡</summary>**
> 
> We can think of a **Playbook** as an **SOP (Standard Operating Procedure)** for when a certain Incident happens.
> 
> In general, every Organization has different Playbooks.
> 
> There’s actually a Playbook functionality built into **Azure** ➜ but we’re trying not to use those automated tools in these labs.
> 
> This is because we want to get a better sense of the “Methodologies” behind **Incident Response**.
> 
> Instead of just trying to learn tools that are specific to Azure, for example.
> 
> The goal here it to get some practice on how someone would **Respond to Incidents in a Real SOC Environment**.
> 
>   </details>

<br>

<h2></h2>

<br>

### Step 4️⃣ ➜ Post-Incident Activity

- Document Findings

- Close out the Incident in Sentinel

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Incident ❶ - Brute Force SUCCESS - Windows</h2> </summary>
<br>

> <details close> 
>   
> **<summary> 💡 </summary>**
> 
> This Incident gets triggered when Sentinel detects a **Successful Login after Multiple Failed Attempts**.
> 
> It indicates that a **Brute Force Attack was Successfully Conducted**.
> 
>   </details>

<br>

## Incident Description

<br>

➡️ This Incident involves observation of potential **Brute Force Attempts against a Windows VM**.

<br>

![azure portal](https://github.com/user-attachments/assets/9c1cce53-082a-4c9e-b6d5-7da25a14a9d7)

<br>

<br>

## Initial Response Actions

- Verify the Authenticity of the Alert or Report.

- Immediately Isolate the Machine and Change the Password of the affected User.

- Identify the Origin of the Attacks and determine if they are attacking or involved with anything else.

- Determine How and When the attack occurred.

  - Are the NSGs not being locked down? If so ➜ check other NSGs.

- Assess the Potential Impact of the Incident.

  - What Type of Account was it? What Permissions did it have?

<br>

<br>

## Detection & Analysis

<details close> 
<summary> <h3>🎯 Step-by-Step</h3> </summary>

<br>
  
**1️⃣** Set the **Severity**, the **Status** & the **Owner** of the Incident:

<br>

![azure portal](https://github.com/user-attachments/assets/014f7990-1462-435d-814c-b637a0cc8fe1)

<br>

<h2></h2>

<br>

**2️⃣** **View Full Details**

<br>

![azure portal](https://github.com/user-attachments/assets/85192897-8e6b-4373-9056-1119fd9bde61)

<br>

<h2></h2>

<br>

**3️⃣** Observe the **Activity Log**

<br>

**```Nothing to show here.```**

<br>

<h2></h2>

<br>

**4️⃣** Observe the **Entities** & **Incident Timeline**

<br>

![azure portal](https://github.com/user-attachments/assets/f3c2a5d6-044c-469d-b70a-c066fe2a29e3)

<br>

<h2></h2>

<br>

**5️⃣** **Investigate the Incident** and continue trying to **Determine the Scope**

<br>

![azure portal](https://github.com/user-attachments/assets/80a9eedd-d292-448f-b591-33c19b0a5936)

<br>

![azure portal](https://github.com/user-attachments/assets/7a073b8d-b577-43b8-885f-7cb587d152e1)

<br>

<h2></h2>

<br>

**6️⃣** **Inspect the Entities** and see if there are any **Related Events**

<br>

The Entity is involved with other **Brute Force Attempts** during the same period.

<br>

![azure portal](https://github.com/user-attachments/assets/e3e70d17-02be-40d5-9832-6c8dc61f05ff)

<br>

<br>

<h2></h2>

<br>

**7️⃣** **Determine Legitimacy** of the Incident

<br>

Determined to be ➜ a **Legitimate Incident** ✅

<br>

<h2></h2>

<br>

**8️⃣** If **True Positive** ➜ Continue | If **False Positive** ➜ Close it out

<br>

Determined to be ➜ a **True Positive** ✅

From the **Investigation** ➜ you can see that the **Attacker / Entity** ```63.143.47.155``` is also involved in **4 other Brute Force Attempt Instances**.

<br>

  </details>

<br>

<br>

## Containment, Eradication & Recovery

<br>

<details close> 
  
**<summary> 💡 Note</summary>**

<br>

I will address this later ➜ in the **Environment Hardening Section**.

Despite that ➜ I'm including the steps here for reference from the **Incident Response Playbook**.

<br>

  </details>

<br>

➡️ **Lock down the NSG** assigned to that VM / Subnet ➜ either **Entirely** or to **Only Allow Necessary Traffic**.

➡️ **Reset** the affected **User’s Password**.

➡️ **Enable MFA**

<br>

<br>

## Post-Incident Activity

<br>

✅ Document Findings and Close out the Incident in Sentinel.

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Incident ❷ - Possible Privilege Escalation - Azure Key Vault</h2> </summary>
<br>

> <details close> 
>   
> **<summary> 💡 </summary>**
> 
> This Incident gets triggered when Sentinel detects Unusual or Unauthorized Access to Critical Credentials in Azure Key Vault.
> 
> For example ➜ when someones unauthorized reads an important Password from our Entreprise Password Manager ➜ Azure Key Vault.
> 
>   </details>

<br>

## Incident Description

<br>

➡️ This Incident involves the unexpected reading of a critical **Secret** from the organization's **Key Vault**.

<br>

<br>

## Initial Response Actions

- Verify the Authenticity of the Alert or Report.

- Identify the Secret that was read and the User or Application that read it.

- Determine How and When the Secret was read.

- Assess the Potential Impact of the Incident.

<br>

<br>

## Detection & Analysis

<details close> 
<summary> <h3>🎯 Step-by-Step</h3> </summary>

<br>
  
**1️⃣** Set the **Severity**, the **Status** & the **Owner** of the Incident:

<br>

![azure portal](https://github.com/user-attachments/assets/6dc6cf54-b40b-47f0-854b-8fbd32c7712b)

<br>

<h2></h2>

<br>

**2️⃣** **View Full Details**

<br>

![azure portal](https://github.com/user-attachments/assets/780dbef7-c579-4fd1-ae9d-7006e0d2ab53)

<br>

<h2></h2>

<br>

**3️⃣** Observe the **Activity Log**

<br>

**```Nothing to show here.```**

<br>

<h2></h2>

<br>

**4️⃣** Observe the **Entities** & **Incident Timeline**

<br>

![azure portal](https://github.com/user-attachments/assets/a5cba627-578f-4911-8a6f-400a9f48ad42)

<br>

<h2></h2>

<br>

**5️⃣** **Investigate the Incident** and continue trying to **Determine the Scope**

<br>

![azure portal](https://github.com/user-attachments/assets/7f13ccd1-e0d0-4857-90eb-c530ed56c491)

<br>

<h2></h2>

<br>

**6️⃣** **Inspect the Entities** and see if there are any Related Events

<br>

![azure portal](https://github.com/user-attachments/assets/4b6f5d37-159f-4bbb-9bee-5b0e973b02b0)

<br>

<h2></h2>

<br>

**7️⃣** **Determine Legitimacy** of the Incident

<br>

Determined **NOT** to be a **Legitimate Incident** ❌

<br>

<h2></h2>

<br>

**8️⃣** If **True Positive** ➜ Continue | If **False Positive** ➜ Close it out

<br>

Determined to be ➜ a **False Positive** ❌

<br>

  </details>

<br>

<br>

## Containment, Eradication & Recovery

<br>

➡️ None.

This was me viewing Key Vault Secrets at work ➜ I'm authorized to do this.

I don't think there is anything wrong with the Rule Logic here ➜ just happened to be a legitimate and authorized Incident-Generating Event.

<br>

<br>

## Post-Incident Activity

<br>

✅ Document Findings and Close out the Incident in Sentinel.

<br>

![azure portal](https://github.com/user-attachments/assets/b0f91414-fa5e-4414-b9da-57c238fccbb4)

<br>

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Incident ❸ - Brute Force SUCCESS - Microsoft Entra ID</h2> </summary>
<br>

> <details close> 
>   
> **<summary> 💡 </summary>**
> 
> The Incident gets triggered when Sentinel detects a Successful Login to a Microsoft Entra ID Account following numerous Failed Login Attempts.
> 
> For example ➜ an Attacker Successfully Accessed a Microsoft Entra ID Account by repeatedly Guessing Passwords.
> 
>   </details>

<br>

## Incident Description

<br>

➡️ This Incident involves Observation of potential **Brute Force Success against Microsoft Entra ID**.

<br>

<br>

## Initial Response Actions

<br>

- Verify the Authenticity of the Alert or Report.

- Immediately Identify and Revoke Sessions/Access for Affected User.

- Identify the Origin of the Attacker & Determine if they are Attacking or Involved with anything else.

- Assess the Potential Impact of the Incident.

  - What Type of Account was it?

  - What Roles did it have?

  - How long has it been since the Breach went Unattended?

<br>

<br>

## Detection & Analysis

<details close> 
<summary> <h3>🎯 Step-by-Step</h3> </summary>

<br>
  
**4️⃣** Observe the **Entities** & **Incident Timeline**

<br>

![azure portal](https://github.com/user-attachments/assets/4316f744-c792-4cba-a7c0-e9e44b00aa3e)

<br>

<h2></h2>

<br>

**5️⃣** **Investigate the Incident** and continue trying to **Determine the Scope**

<br>

![azure portal](https://github.com/user-attachments/assets/c2aa1fce-32ac-4003-a659-a82ee50f319d)

<br>

  </details>

<br>

<br>

## Containment, Eradication & Recovery

<br>

➡️ **Reset** the affected **User’s Password & Roles** if applicable.

➡️ **Enable MFA**.

➡️ Consider preventing any logins from outside the US with **Conditional Access***.

<br>

<br>

## Post-Incident Activity

<br>

✅ Document Findings and Close out the Incident in Sentinel.

<br>

<details close> 
  
**<summary> 📝 Documentation</summary>**

<br>

This is another **False Positive** ❌

It could have been Multiple Login Attempts with the Incorrect Password or MFA Code.

I recognize this IP from work ➜ although I'm not entirely sure how 35 events were produced.

Perhaps by restoring multiple browser tabs simultaneously?
  
  - MFA is already Enabled on the User's Account.
 
  - and the Logins occurred from an Expected IP.

<br>

  </details>

<br>

![azure portal](https://github.com/user-attachments/assets/7453979b-1468-41fe-ab5e-54b7626b59aa)

<br>

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Incident ❹ - Brute Force ATTEMPT - Linux Syslog</h2> </summary>
<br>

> <details close> 
>   
> **<summary> 💡 </summary>**
> 
> This Incident gets triggered when Sentinel detects a series of Consecutive Failed Login Attempts on a Linux Machine, recorded in the Syslog.
> 
>   </details>

<br>

## Incident Description

<br>

➡️ This Incident involves Observation of potential **Brute Force Attempts against a Linux Virtual Machine**.

<br>

<br>

## Initial Response Actions

<br>

- Verify the Authenticity of the Alert or Report.

- Immediately Isolate the Machine & Change the Password of the Affected User.

- Identify the Origin of the Attacks & Determine if they are Attacking or Involved with anything else.

- Determine How and When the Attack occurred.

  - Are the NSGs not being Locked Down? If so ➜ Check other NSGs.

- Assess the Potential Impact of the Incident.

  - What Type of Account was it? Permissions?

<br>

<br>

## Detection & Analysis

<details close> 
<summary> <h3>🎯 Step-by-Step</h3> </summary>

<br>
  
**1️⃣** Set the **Severity**, the **Status** & the **Owner** of the Incident:

<br>

![azure portal](https://github.com/user-attachments/assets/a78aa8c6-5ab7-4229-8d69-61f8c479dc28)

<br>

<h2></h2>

<br>

**5️⃣** **Investigate the Incident** and continue trying to **Determine the Scope**

<br>

![azure portal](https://github.com/user-attachments/assets/a79b05a8-8c0a-4fec-b690-b96051203826)

<br>

![azure portal](https://github.com/user-attachments/assets/aeeb946b-3404-4f60-9a4d-1106374f07bc)

<br>

<h2></h2>

<br>

**6️⃣** **Inspect the Entities** and see if there are any **Related Events**.

<br>

![azure portal](https://github.com/user-attachments/assets/c3cbf772-7e0b-4ad2-967e-9c2b70924f57)

<br>

![azure portal](https://github.com/user-attachments/assets/478d9be9-7822-4b30-a9c5-cdfafcf5cb70)

<br>

![azure portal](https://github.com/user-attachments/assets/47a651e6-3887-42b7-bfc8-fba3ef30d281)

<br>

![azure portal](https://github.com/user-attachments/assets/3aed1986-18eb-4bfd-93d9-f358b77592a9)

<br>

![azure portal](https://github.com/user-attachments/assets/10fe187d-3898-4edf-b276-bdc4b89fe7e4)

<br>

![azure portal](https://github.com/user-attachments/assets/fadc1a2e-eb84-4f70-a48b-24dbe452c3f0)

<br>

  </details>

<br>

<br>

## Containment, Eradication & Recovery

<br>

➡️ **Lock down the NSG** assigned to that VM / Subnet ➜ either **Entirely** or to **Only Allow Necessary Traffic**.

➡️ **Reset** the affected **User’s Password & Roles** if applicable.

➡️ **Enable MFA**.


<br>

<br>

## Post-Incident Activity

<br>

✅ Document Findings and Close out the Incident in Sentinel.

<br>

<details close> 
  
**<summary> 📝 Documentation</summary>**

<br>

There are **6 Entities** (218.92.0.118, 151.80.184.123, 123.49.33.102, 43.134.54.244, 43.156.227.146, 165.22.62.136) ➜ Attacking this Linux Virtual Machine ➜ with No Successful Attempts.

There is a total of **30 Events** grouped into **5 Alerts**.

⚠️ Suspected Over-Exposure to the Public Internet.

<br>

  </details>

<br>

![azure portal](https://github.com/user-attachments/assets/240f7483-122a-4ce0-883f-bd09c5ef7af4)

<br>

<br>

  </details>

<h2></h2>

<br>

<br>

<br>

<br>

<br>

<br>

<br>
  
<br>
