Grant access to Managed Identity Script

<pre lang="markdown">Import-Module Microsoft.Graph.Authentication
Import-Module Microsoft.Graph.Applications
$tenantId = "<>"        # Your tenant ID
$MSIName = ""; # Name of your managed identity
# Log in as a user with the "Privileged Role Administrator" role
Connect-MgGraph -TenantId $tenantId -Scopes "AppRoleAssignment.ReadWrite.All,Application.Read.All"
# Search for Microsoft Graph
$MSGraphSP = Get-MgServicePrincipal -Filter "DisplayName eq 'Microsoft Graph'";
$MSGraphSP

$MSI = Get-MgServicePrincipal -Filter "DisplayName eq '$MSIName'"
if($MSI.Count -gt 1)
{
Write-Output "More than 1 principal found with that name, please find your principal and copy its object ID. Replace the above line with the syntax $MSI = Get-MgServicePrincipal -ServicePrincipalId <your_object_id>"
Exit
}
# Get required permissions
$Permissions = @(
  "User.RevokeSessions.All"
)
# Find app permissions within Microsoft Graph application
$MSGraphAppRoles = $MSGraphSP.AppRoles | Where-Object {($_.Value -in $Permissions)}
# Assign the managed identity app roles for each permission
foreach($AppRole in $MSGraphAppRoles)
{
    $AppRoleAssignment = @{
        principalId = $MSI.Id
        resourceId = $MSGraphSP.Id
        appRoleId = $AppRole.Id
    }
New-MgServicePrincipalAppRoleAssignment -ServicePrincipalId $AppRoleAssignment.PrincipalId -BodyParameter $AppRoleAssignment -Verbose
}</pre>
This PowerShell script:

* Imports Microsoft Graph modules
* Connects to Microsoft Graph with required scopes
* Finds the **Microsoft Graph service principal** and a **managed identity** by name
* Assigns the **`User.RevokeSessions.All`** app role permission from Microsoft Graph to the managed identity

It's used to **grant a managed identity permission** to revoke user sessions via Microsoft Graph.
