EmailEvents
| where SenderFromAddress == "<user_principle_name>"

AuditLogs
| where InitiatedBy['user']['userPrincipalName'] == "<user_principle_name>"

SigninLogs
| where "<user_principle_name>"


UrlClickEvents
| where AccountUpn == "<user_principle_name>"

EmailEvents
| where SenderFromAddress == "<user_principle_name>"


search "<user_principle_name>"


OfficeActivity
| where UserId == "<user_principle_name>"


search "<user_principle_name>"
| summarize by $table
