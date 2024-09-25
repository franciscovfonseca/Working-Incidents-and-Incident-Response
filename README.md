<br>

<h1 align="center">Working Incidents & Incident Response</h1>

<br>

In this lab we're going to **Investigate & Work Incidents** being generated within **Microsoft Sentinel**.

We'll do this in accordance with the [**NIST 800-61**](https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-61r2.pdf) **Incident Management Lifecycle**.

<br>

  <details close> 
  
**<summary> 📌 Overview</summary>**

We'll practice **Incident Response**.

We can see that we have accumulated a decent number of **Incidents** over the last 24 Hours:

<br>

![azure portal](https://github.com/user-attachments/assets/375cac7f-3610-4d11-9cbd-8639ff7e54b4)

<br>

So we’re going to take our time and work our way through some of these ➜ as if we’re working in a real **SOC Environment**.

As previously mentioned ➜ we'll practice the **NIST 800-61 Incident Management Lifecycle**.

💡 In reality ➜ every Organization practices **Incident Response** a little differently than one another.

<br>

We won’t be using here the “absolute best way” to do **Incident Response** ➜ but we’ll be adhering to the **NIST 800-61 Lifecycle** of:

**1️⃣ Preparation**

**2️⃣ Detection & Analysis**

**3️⃣	Containment, Eradication & Recovery**

**4️⃣	Post-Incident Activity**

  </details>

<p align="center">
<img width="750" src="https://github.com/user-attachments/assets/66745d60-fc59-406b-9955-b371304e4d98" alt="Banner"/>

<br>

<br>

<details close>   
<summary> <h2>📝 Incident Response Guidelines</h2> </summary>
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
> **<summary> 💡 Context</summary>**
> 
> This phase gets kicked off when someone notices some kind of **Anomaly in the System**.
> 
> In our case we configured a bunch of Alerts ➜ and the fact that an **Incident was Created** ➜ is the beggining of our **Detection Phase**.
> 
>   </details>

<br>

|                   | **Action**                                 |
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

We'll use this simple [**Incident Response PlayBook**](https://docs.google.com/document/d/1Cua7Kz3Y0OZuPUS0-Q1H7jbwGbYeDq1WISIHrdRk-MY/edit#heading=h.85wjqnr3yu96) to **Remediate the Incidents**.

<br>

>   <details close> 
>   
> **<summary> 💬</summary>**
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

- Document Findings.

- Close out the Incident in Sentinel.

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

![azure portal](https://github.com/user-attachments/assets/431719cf-bbda-4eca-a812-1aff0beeff76)

<br>

<br>

## Initial Response Actions

- Verify the Authenticity of the Alert or Report.

- Immediately Isolate the Machine and Change the Password of the affected User.

- Identify the Origin of the Attacks and determine if they are attacking or involved with anything else.

- Determine How and When the attack occurred.

  - Are the NSGs not being locked down? If so ➜ check other NSGs.

- Assess the Potential Impact of the Incident.

  - What Type of Account was it?
  - What Permissions did it have?

<br>

<br>

## Detection & Analysis

<details close> 
<summary> <h3>🎯 Step-by-Step</h3> </summary>

<br>
  
**1️⃣** Set the **Severity**, the **Status** & the **Owner** of the Incident:

<br>

![azure portal](https://github.com/user-attachments/assets/90c4ed73-7422-4b42-81bf-ca16da3143db)

<br>

<h2></h2>

<br>

**2️⃣** **View Full Details**

<br>

![azure portal](https://github.com/user-attachments/assets/227d3761-f3e7-43cc-9179-fffe892bae35)

<br>

<h2></h2>

<br>

**3️⃣** Observe the **Activity Log**

<br>

![azure portal](https://github.com/user-attachments/assets/20a9f513-b280-460a-9794-f5ff20866cf2)

<br>

<h2></h2>

<br>

**4️⃣** Observe the **Entities** & **Incident Timeline**

<br>

![azure portal](https://github.com/user-attachments/assets/a1298519-54ae-41cd-9582-a03881e9ba45)

<br>

![azure portal](https://github.com/user-attachments/assets/0b651bae-eb40-4d42-8c78-0858d92e1f1a)

<br>

<h2></h2>

<br>

**5️⃣** **Investigate the Incident** and continue trying to **Determine the Scope**

<br>

![azure portal](https://github.com/user-attachments/assets/9a118c0d-3101-4298-9db1-f5d3209d0be4)

<br>

![azure portal](https://github.com/user-attachments/assets/526d2fe2-a7bb-4ddb-bf37-5a94afc98ff6)

<br>

<h2></h2>

<br>

**6️⃣** **Inspect the Entities** and see if there are any **Related Events**

<br>

The Entity is involved with other **Brute Force Attempts** during the same period.

<br>

![azure portal](https://github.com/user-attachments/assets/b9cca918-8351-47f4-8590-c34c686f56b1)

<br>

![azure portal](https://github.com/user-attachments/assets/f03743dc-f5cf-4b05-abc1-5aee5034dcc7)

<br>

<h2></h2>

<br>

**7️⃣** **Determine Legitimacy** of the Incident

<br>

![azure portal](https://github.com/user-attachments/assets/82c05168-8085-4f3e-a5c5-f13b103e445d)

<br>

Determined to be ➜ a **Legitimate Incident** ✅

<br>

<h2></h2>

<br>

**8️⃣** If **True Positive** ➜ Continue | If **False Positive** ➜ Close it out

<br>

Determined to be ➜ a **False Positive** ❌

⚠️ From the **Investigation** ➜ you can see that the **Attacker / Entity** ```186.96.10.36``` is also involved in **4 other Brute Force Attempt Instances**.

<br>

  </details>

<br>

<br>

## Containment, Eradication & Recovery

<br>

We will address this later ➜ in the **Environment Hardening Section**.

Despite that ➜ I'm including the steps here for reference from the **Incident Response Playbook**:

<br>

➡️ **Lock down the NSG** assigned to that VM / Subnet ➜ either **Entirely** or to **Only Allow Necessary Traffic**.

➡️ **Reset** the affected **User’s Password**.

➡️ **Enable MFA**

<br>

<br>

## Post-Incident Activity

<br>

**Document Findings** & **Close out the Incident** in Microsoft Sentinel:

✅ Closing out Incident as **False-Positive** ➜ but we'll start the processes for Hardening the NSGs.

<br>

<details close> 
  
**<summary> Close The Incident</summary>**

<br>

We'll go back to **Microsoft Sentinel** to change the **Status** of the Incident to ☑️ **Closed**:

<br>

![azure portal](https://github.com/user-attachments/assets/15c38b88-969d-4bfc-90bc-7ecd40e39a0d)

<br>

In the **"Comment"** section we'll paste the **Incident Notes** we took throughout this whole **Incident Response Process**:

<br>

![azure portal](https://github.com/user-attachments/assets/1c7f7a2b-f29c-4230-b460-ed38dd78b045)

<br>

![azure portal](https://github.com/user-attachments/assets/7921f660-46eb-40de-9e73-18bbc88b1290)

<br>

  </details>

<br>

<details close> 
  
**<summary> Lockdown the NSG</summary>**

<br>

Back in the **Azure Portal** ➜ we'll go to our ```windows-vm``` ➜ and click on the **Networking** blade:

<br>

![azure portal](https://github.com/user-attachments/assets/ff1732dd-8164-4753-97e0-36d14b2f9304)

<br>

Then inside of the Windows VM's **NSG** ➜ we'll Edit the existent **Inbound Security Rule**:

<br>

![azure portal](https://github.com/user-attachments/assets/54a56406-0756-40a6-ace5-5afb907f32c1)

<br>

We'll Edit it so that we only **Allow Inbound Traffic** from our own **IP Address**:

<br>

![azure portal](https://github.com/user-attachments/assets/e990e8df-a8ee-4ace-853a-58d5e3016011)

<br>

We're also going to delete the existent **RDP Rule** ➜ that **Allows anyone to RDP into our VM** ➜ which we don't want:

<br>

![azure portal](hhttps://github.com/user-attachments/assets/3e66f53c-d366-4be0-b6f1-f041832f765e)

<br>

  </details>

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
> This Incident gets triggered when Sentinel detects **Unusual or Unauthorized Access to Critical Credentials in Azure Key Vault**.
> 
> For example ➜ when someone unauthorized **Reads an Important Password** from our Entreprise Password Manager (AKA **Azure Key Vault**).
> 
>   </details>

<br>

## Incident Description

<br>

➡️ This Incident involves the unexpected reading of a critical **Secret** from the organization's **Key Vault**.

<br>

![azure portal](https://github.com/user-attachments/assets/63529b63-52bc-41be-9535-e7d4c94b767f)

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

![azure portal](https://github.com/user-attachments/assets/abb13e8c-d91a-4119-a137-230a9156bfc4)

<br>

<h2></h2>

<br>

**2️⃣** **View Full Details**

<br>

![azure portal](https://github.com/user-attachments/assets/088420b3-aff8-4102-940b-b8a778cb2c4d)

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

![azure portal](https://github.com/user-attachments/assets/f87b52e8-9ca0-4f16-9af5-7c792d939c8b)

<br>

<h2></h2>

<br>

**5️⃣** **Investigate the Incident** and continue trying to **Determine the Scope**

<br>

![azure portal](https://github.com/user-attachments/assets/c71a0927-1c28-4937-befe-48cece22c2cd)

<br>

<h2></h2>

<br>

**6️⃣** **Inspect the Entities** and see if there are any **Related Events**

<br>

![azure portal](https://github.com/user-attachments/assets/15e05e51-adc7-482c-8889-82575d5e7549)

<br>

![azure portal](https://github.com/user-attachments/assets/d1db1e9a-0cc3-4b9f-af8d-e20e09c20ec9)

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

This was me **Viewing Key Vault Secrets** ➜ I'm authorized to do this.

I don't think there is anything wrong with the **Rule Logic** here ➜ just happened to be a **Legitimate & Authorized Incident-Generating Event**.

<br>

<br>

## Post-Incident Activity

<br>

**Document Findings** & **Close out the Incident** in Microsoft Sentinel:

✅ Closing out Incident as **False-Positive** ❌

<br>

<details close> 
  
**<summary> Close The Incident</summary>**

<br>

We'll go back to **Microsoft Sentinel** to change the **Status** of the Incident to ☑️ **Closed**:

<br>

![azure portal](https://github.com/user-attachments/assets/23db75e0-ab91-4bb1-b703-b98cb289026a)

<br>

In the **"Comment"** section we'll paste the **Incident Notes** we took throughout this **Incident Response Lifecycle**:

<br>

![azure portal](https://github.com/user-attachments/assets/c3729286-e197-4d77-b2f2-40267ac258e0)

<br>

![azure portal](https://github.com/user-attachments/assets/db0c2811-76a4-4917-8820-f0a8f3bb905b)

<br>

  </details>

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Incident ❸ - Brute Force ATTEMPT - Linux Syslog</h2> </summary>
<br>

> <details close> 
>   
> **<summary> 💡 </summary>**
> 
> This Incident in Microsoft Sentinel is Triggered when a **Brute Force Attack Successfully Gains Access to a Linux System**.
> 
> This means an **Unauthorized User has Guessed the Correct Password** after Multiple Attempts, as recorded in the **Linux Syslog**.
> 
>   </details>

<br>

## Incident Description

<br>

➡️ This Incident involves Observation of potential **Brute Force Attempts against a Linux Virtual Machine**.

<br>

![azure portal](https://github.com/user-attachments/assets/a5c62bca-a131-44a4-8edd-662b73da3d56)

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

![azure portal](https://github.com/user-attachments/assets/7cee8d19-76a0-466c-ad02-73dd74e9ad39)

<br>

<h2></h2>

<br>

**2️⃣** **View Full Details**

<br>

![azure portal](hhttps://github.com/user-attachments/assets/6677e822-a9ef-4cbf-8968-35e2c2acb280)

<br>

<h2></h2>

<br>

**3️⃣** Observe the **Activity Log**

<br>

**```Nothing to show here.```**

<br>

![azure portal](https://github.com/user-attachments/assets/a895fc1b-1b43-41d3-9f59-efcd6dc3cbf7)

<br>

<h2></h2>

<br>

**4️⃣** Observe the **Entities** & **Incident Timeline**

<br>

![azure portal](https://github.com/user-attachments/assets/e9e4d1dc-0e95-49c5-bf00-6156fb09094a)

<br>

<h2></h2>

<br>

**5️⃣** **Investigate the Incident** and continue trying to **Determine the Scope**

<br>

![azure portal](https://github.com/user-attachments/assets/ffc7a810-f487-4ba4-8c88-ca1201b8d6a9)

<br>

![azure portal](https://github.com/user-attachments/assets/f12f40f7-798d-4e10-b585-d3e78ec3aacf)

<br>

<h2></h2>

<br>

**6️⃣** **Inspect the Entities** and see if there are any **Related Events**.

<br>

![azure portal](hhttps://github.com/user-attachments/assets/e2e42a74-3de9-43fe-a211-1830c435fa60)

<br>

![azure portal](https://github.com/user-attachments/assets/987c05c8-215b-4966-a7f3-01cca8cc2ed3)

<br>

<h2></h2>

<br>

**7️⃣** **Determine Legitimacy** of the Incident

<br>

Determined to be ➜ a **Legitimate Incident** ✅

<br>

![azure portal](https://github.com/user-attachments/assets/77b140f9-02bd-4f41-b215-f529604f82c3)

<br>

<h2></h2>

<br>

**8️⃣** If **True Positive** ➜ Continue | If **False Positive** ➜ Close it out

<br>

Determined to be ➜ a **True Positive** ✅

<br>


  </details>

<br>

<br>

## Containment, Eradication & Recovery

<br>

<details close> 
  
**<summary> ➡️ Lock down the NSG assigned to that VM / Subnet</summary>**

<br>

Inside the **Azure Portal** ➜ we'll go to our ```linux-vm``` ➜ and click on the **Networking** blade:

<br>

![azure portal](https://github.com/user-attachments/assets/cc0f5d16-c02d-4867-a60b-aacef9bc2a05)

<br>

Then inside of the Linux VM's **NSG** ➜ we'll Delete the First 2 Existent **Custom Security Rules**:

<br>

![azure portal](https://github.com/user-attachments/assets/46f75b40-3f75-4a0a-9716-38840b5226fa)

<br>

We'll then **Add a New Inbound Security Rule** ➜ so that we only **Allow Inbound Traffic** from our own **IP Address**:

<br>

![azure portal](https://github.com/user-attachments/assets/5e6cebf7-c730-4b12-85f6-849e59b4627d)

<br>

  </details>

<br>

<details close> 
  
**<summary> ➡️ Reset the Affected User’s Password</summary>**

<br>

We'll go to our Virtual Machine ```linux-vm``` ➜ and click on the **Reset password** blade:

<br>

![azure portal](https://github.com/user-attachments/assets/5b1b6323-37ed-4cfa-b506-03627168b549)

<br>

Then we'll just **Reset the Password** of ```labuser``` to a Strong Password ➜ and click on 💾 **Update**

<br>

![azure portal](https://github.com/user-attachments/assets/60a644f9-7610-40fe-924e-7764b2e2db6b)

<br>

  </details>

<br>

➡️ **Enable MFA** ➜ *We'll do this in Subsequent Labs*.

<br>

<br>

## Post-Incident Activity

<br>

**Document Findings** & **Close out the Incident** in Microsoft Sentinel:

✅ Closing out Incident as **True Positive**

<br>

<details close> 
  
**<summary> Close The Incident</summary>**

<br>

We'll go back to **Microsoft Sentinel** to change the **Status** of the Incident to ☑️ **Closed**:

<br>

![azure portal](https://github.com/user-attachments/assets/731a392f-d540-4853-b431-493795278a0e)

<br>

In the **"Comment"** section we'll paste the **Incident Notes** we took:

<br>

![azure portal](https://github.com/user-attachments/assets/b9cd0a2a-33d5-44da-84aa-76d5d589276f)

<br>

![azure portal](https://github.com/user-attachments/assets/4800befa-0e58-4b74-b792-07e8731b148c)

<br>

  </details>

<br>

  </details>

<h2></h2>

<details close> 
<summary> <h2>Incident ❹ - Malware Detected</h2> </summary>
<br>

> <details close> 
>   
> **<summary> 💡 </summary>**
> 
> A **Malware Detected Incident** indicates that a **Malicious Software** was identified on a System or Network.
> 
> This Incident get Triggered when Sentinel detects **Suspicious Files or Activities** matching known **Malware Patterns**.
> 
>   </details>

<br>

## Incident Description

<br>

➡️ This Incident involves **Malware being Detected** on a Workstation:
  
  - Potentially compromising the **Confidentiality**, **Integrity**, or **Availability** of the System and Data.

<br>

![azure portal](https://github.com/user-attachments/assets/57770c1a-e094-4aed-b44d-9a199975fe7c)

<br>

<br>

## Initial Response Actions

<br>

- Verify the Authenticity of the alert or report.

- Identify the Primary User Account of the System (if applicable).

- Notify any Affected Stakeholders ➜ such as Users or Customers (as appropriate) and provide them with guidance on:
  - How to Protect Themselves from Potential Harm.

- Run a Full System Scan ➜ using an up-to-date Antivirus Software to Identify and Remove the Malware.

- If the Malware cannot be Removed or is suspected to have caused Significant Damage:
  - Shut Down the Workstation and Disconnect it from the Network.


<br>

<br>

## Detection & Analysis

<details close> 
<summary> <h3>🎯 Step-by-Step</h3> </summary>

<br>
  
**1️⃣** Set the **Severity**, the **Status** & the **Owner** of the Incident:

<br>

![azure portal](https://github.com/user-attachments/assets/b53ae208-84d6-4136-9bce-16559c380c8a)

<br>

<h2></h2>

<br>

**2️⃣** **View Full Details**

<br>

![azure portal](https://github.com/user-attachments/assets/b37f3f5c-192b-493c-8cfa-fd5aae8e9acd)

<br>

<h2></h2>

<br>

**3️⃣** Observe the **Activity Log**

<br>

![azure portal](https://github.com/user-attachments/assets/e5ef444f-1be5-4538-9e0d-ec3ace4caada)

<br>

<h2></h2>

<br>

**4️⃣** Observe the **Entities** & **Incident Timeline**

<br>

![azure portal](https://github.com/user-attachments/assets/76799c81-96cd-4185-a54c-ccc30a390da6)

<br>

<h2></h2>

<br>

**5️⃣** **Investigate the Incident** and continue trying to **Determine the Scope**

<br>

![azure portal](https://github.com/user-attachments/assets/09a74895-082c-431a-ba59-06bf46750159)

<br>

<h2></h2>

<br>

**6️⃣** **Inspect the Entities** and see if there are any **Related Events**.

<br>

![azure portal](https://github.com/user-attachments/assets/a0919c77-fd51-46a3-ae65-9ebb0bce9fd1)

<br>

![azure portal](https://github.com/user-attachments/assets/58e75b0e-ad9c-4f5a-9937-ef686f028acb)

<br>

<h2></h2>

<br>

**7️⃣** **Determine Legitimacy** of the Incident

<br>

Determined to be ➜ a **Legitimate Incident** ✅

<br>

💡 Here is the **UPDATED Query** we used for **Detecting Malware**:

```commandline
// Malware Detection
Event
| where EventLog == "Microsoft-Windows-Windows Defender/Operational"
| where EventID == "1116" or EventID == "1117"
```
<br>

![azure portal](https://github.com/user-attachments/assets/39df6768-6588-42f9-a0f7-653ee64f0518)

<br>

All of these Alerts have **No Action necessary** ➜ it looks like they were Remediated:

```Microsoft Antimalware has taken action to protect this machine from malware or other pottentially unwanted Software```

<br>

<h2></h2>

<br>

**8️⃣** If **True Positive** ➜ Continue | If **False Positive** ➜ Close it out

<br>

✅ Determined to be ➜ a **False Positive** ❌

<br>

As far as **Malware** goes ➜ this Alert was a **False Positive** because it looks like the User was testing with **EICAR Files**.

💡 This is the **Query** we used to Identify what **Type of Malware was Detected**:

```commandline
SecurityAlert
| where AlertType == "AntimalwareActionTaken"
| where CompromisedEntity == "windows-vm"
| where RemediationSteps !has "No user action is necessary"
| where ExtendedProperties !has "EICAR"
```
<br>

![azure portal](https://github.com/user-attachments/assets/c75c6107-3fe4-4384-95ef-02856c780b71)

<br>

📝 Corroborated with User and User's Manager.

<br>

  </details>

<br>

<br>

## Containment, Eradication & Recovery

<br>

➡️ None:

We don't need to **Contain, Eradicate or Recover** anything ➜ because it's just an **EICAR File**.

<br>

<br>

## Post-Incident Activity

<br>

**Document Findings** & **Close out the Incident** in Microsoft Sentinel:

✅ Closing out Incident as **False Positive** ❌

<br>

<details close> 
  
**<summary> Close The Incident</summary>**

<br>

We'll go back to **Microsoft Sentinel** to change the **Status** of the Incident to ☑️ **Closed**.

- **Reason for Closing**: ```Benign Positive - Suspicious but expected```

<br>

![azure portal](https://github.com/user-attachments/assets/429679f0-09c8-4285-9933-7cc7bd74d250)

<br>

In the **"Comment"** section we'll paste the **Incident Notes** we took:

<br>

![azure portal](https://github.com/user-attachments/assets/5c0b7b10-8f53-4408-99da-51b803d12349)

<br>

![azure portal](https://github.com/user-attachments/assets/eca7c3c8-adc4-4489-9cb9-d7b89661b412)

<br>

  </details>

<br>

<h2></h2>

  </details>

<br>

<br>

<br>

<br>

<br>

<br>

<br>
  
<br>
