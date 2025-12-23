# Active Directory – Post-Installation Configuration

This phase focuses on configuring and validating core services after the successful installation of **Windows Server 2019 Active Directory Domain Services (AD DS)**. The objective is to make the domain operational by configuring DNS, DHCP, and certificate services before user management and policy enforcement.

---

## Video Demonstration
*(Optional – add later if recorded)*  
YouTube: **Active Directory Tutorial (Phase 2/3) – Post-Installation Configuration**

---

## Environments and Technologies Used

- VirtualBox
- pfSense Firewall
- Active Directory Domain Services (AD DS)
- DNS
- DHCP
- Active Directory Certificate Services (AD CS)
- PowerShell

---

## Operating Systems Used

- Windows Server 2019  
- pfSense

---

## OVERVIEW

1. Configure DNS forwarders for external name resolution.
2. Install and configure DHCP services.
3. Configure Active Directory Certificate Services (AD CS).
4. Validate core domain services.
5. Prepare the environment for user management and Group Policy configuration.

---

## 1. DNS Post-Installation Configuration

Configure DNS forwarders to allow domain systems to resolve external domains.

- Open **DNS Manager**.
- Select the domain controller (**DC1**).
- Navigate to **Forwarders**.
- Add the following forwarder:
  - `10.80.80.1`
- Apply and confirm changes.

---

## 2. DHCP Server Installation

Install the DHCP Server role and complete initial configuration.

- Open **Server Manager → Add Roles and Features**.
- Select **DHCP Server**.
- Add required features.
- Complete the DHCP post-installation configuration wizard.

---

## 3. DHCP Scope Configuration

Create a DHCP scope to assign IP addresses to domain clients.

- Scope Name: `AD Lab`
- Start IP: `10.80.80.11`
- End IP: `10.80.80.25`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `10.80.80.1`
- Lease Duration: `365 days`
- Activate the scope.

---

## 4. Active Directory Certificate Services (AD CS)

Install and configure certificate services for secure authentication.

- Add **Active Directory Certificate Services** role.
- Configure Certification Authority:
  - Enterprise CA
  - Root CA
- Complete configuration using default settings.

---

## 5. Validation and Testing

Verify that all services are functioning correctly.

- Confirm DHCP leases are being issued.
- Validate DNS resolution for internal and external domains.
- Confirm AD DS services are running.
- Review Event Viewer for errors or warnings.

---

## Conclusion

This phase completes the core configuration required for a functional Active Directory environment. With DNS, DHCP, and certificate services configured and validated, the domain is now ready for **user creation, Group Policy configuration, and security testing** in Phase 3.
