Download Microsoft Graph cmd to Powershell
<pre lang="markdown"> Connect-MgGraph -Scopes "Group.Readwrite.All", "User.ReadWrite.All" </pre>
g
<pre lang="markdown">Start-ADSyncSyncCycle -PolicyType Delta</pre> is a PowerShell command that triggers a delta sync in Azure AD Connect, syncing only recent changes (not a full sync) between on-premises Active Directory and Azure AD.
