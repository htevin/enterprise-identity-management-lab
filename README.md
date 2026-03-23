# 🔐 Enterprise Identity Management & RBAC Implementation (Microsoft Entra ID)



## 📌 Project Overview
This project demonstrates the end-to-end administration of digital identities and access controls within a Microsoft Entra ID (formerly Azure AD) environment. Using a simulated enterprise scenario ("Wayne Enterprises / The Justice League"), this lab highlights the practical application of core Identity and Access Management (IAM) principles, including user lifecycle management, role-based access control (RBAC), licensing, and B2B external collaboration.

This repository serves as a practical showcase of the skills required for modern identity administration and aligns directly with the competencies of the Microsoft Identity and Access Administrator (SC-300) certification.

## 🛠️ Skills & Technologies Demonstrated
* **Identity Platform:** Microsoft Entra ID, Microsoft 365 Admin Center
* **User Lifecycle Management:** Single-user provisioning, bulk importing (CSV with strict schema adherence), and offboarding.
* **Access Management:** Role-Based Access Control (RBAC), Least Privilege principles.
* **External Identities:** B2B Collaboration, Guest User provisioning.
* **License Management:** Automated and manual license assignment for SaaS applications.

## 📖 Business Scenario
"Wayne Enterprises" requires a secure, scalable identity solution to manage its specialized task force. As the acting Identity Administrator, the objective is to provision internal accounts, assign appropriate M365 licenses for operational tools, invite external inter-galactic consultants, grant scoped directory permissions based on the principle of least privilege, and bulk-onboard the rest of the team during a high-volume hiring phase.

---

## 🚀 Step-by-Step Implementation

### Phase 1: Single User Provisioning
Established a standard internal member account with secure, auto-generated credentials to create a baseline directory footprint.

1. Navigated to the [Microsoft Entra admin center](https://entra.microsoft.com) and authenticated using Tenant administrator credentials.
2. From the left navigation menu, selected **Users** > **All users**.
3. Initiated **+ New user** > **Create new user**.
4. Entered the core identity attributes:
   * **User principal name:** Clark.K@gcamlifetsyle.onmicrosoft.com
   * **Display name:** Clark Kent
  <p>
<img src="https://imgur.com/fBfTsh0.png" height="80%" width="80%""/>
</p>
5. Selected the **Properties** tab and configured identity values (First name: Clark, Last name: Kent).
6. Configured the **Usage location** to **United States** to ensure compliance for future service license assignments.
7. Selected **Review + create**, then **Create**.
8. Validated successful deployment by querying the directory.
<p>
<img src="https://imgur.com/9AvFZBc.png" height="80%" width="80%""/>
</p>

### Phase 2: License Allocation
Assigned necessary SaaS product licenses to enable productivity and automated workflows without over-provisioning resources.

1. Navigated to the [Microsoft 365 admin center](https://admin.microsoft.com).
2. Expanded the **Billing** menu and selected **Licenses**.
3. Selected an available operational license (e.g., **Microsoft Power Automate Free**).
4. Selected **+ Assign licenses** and targeted the **Clark Kent** user object.
  <p>
<img src="https://imgur.com/bpgrehG.png" height="80%" width="80%""/>
</p>
5. Executed the assignment and verified the success notification.
 <p>
<img src="https://imgur.com/iz0zWdx.png" height="80%" width="80%""/>
</p>

### Phase 3: B2B External Collaboration
Invited an external identity into the tenant to facilitate cross-organizational collaboration while maintaining strict tenant boundary security.

1. In the Microsoft Entra admin center, navigated to **Identity** > **Users** > **All users**.
2. Selected **+ New User** > **Invite external user**.
3. Configured the external collaborator profile:
   * **Email:** Thor@avengers-mansion.com *(Used a controlled test email for validation)*
   * **Display name:** Thor Odinson
   * **Message:** "Greetings, Odinson. Thank you for joining the cross-universe initiative. We look forward to battling this threat together."
 <p>
<img src="https://imgur.com/VwuPbdZ.png" height="80%" width="80%""/>
</p>
4. Selected **Review + Create**, then **Create**.

### Phase 4: Role-Based Access Control (RBAC)
Delegated specific administrative permissions using Entra ID built-in roles, strictly adhering to auditing and least privilege standards.

1. Located the **Clark Kent** user profile in Entra ID.
2. Navigated to **Assigned roles** > **+ Add assignment**.
3. Selected the **Attribute Definition Reader** role to grant directory read access without global read/write privileges.
4. Set the **Assignment type** to **Eligible** (or Active).
5. Documented the administrative action: *"User requires directory read access for primary duties."*
7. Selected **Assign**.
<p>
<img src="https://imgur.com/de6EgIO.png" height="80%" width="80%""/>
</p>   

### Phase 5: Bulk User Lifecycle Management
Streamlined the onboarding process for multiple identities simultaneously via CSV upload, successfully managing schema formatting and tenant domain routing.

1. Navigated to **Identity** > **Users** > **All users**.
2. Selected **Bulk operations** > **Bulk create** and downloaded the strict CSV schema template.
3. Populated the template with compliant data, retaining the mandatory `version:v1.0` header row and aligning UPNs with the verified tenant domain:
   * Diana Prince (Wonder Woman)
   * Barry Allen (The Flash)
   * Arthur Curry (Aquaman)
  <p>
<img src="https://imgur.com/mjZjzwe.png" height="80%" width="80%""/>
</p>   
4. Uploaded `JusticeLeague_Roster.csv` to the Entra ID portal.
    <p>
<img src="https://imgur.com/is6bKqL.png" height="80%" width="80%""/>
</p>  
5. Executed the bulk operation and refreshed the directory to confirm successful batch provisioning.
 <p>
<img src="https://imgur.com/4hiB2yi.png" height="80%" width="80%""/>
</p> 

---
*Disclaimer: This repository is for educational and portfolio demonstration purposes. No actual Kryptonians or Asgardians were harmed during the making of this lab.*
