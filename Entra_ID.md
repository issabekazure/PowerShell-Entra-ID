<pre lang="markdown"> Connect-MgGraph -Scopes "Group.Readwrite.All", "User.ReadWrite.All" </pre> is a PowerShell command that connects to Microsoft Graph with permissions to read/write groups and read/write users.

<pre lang="markdown">Start-ADSyncSyncCycle -PolicyType Delta</pre> is a PowerShell command that triggers a delta sync in Azure AD Connect, syncing only recent changes (not a full sync) between on-premises Active Directory and Azure AD.
