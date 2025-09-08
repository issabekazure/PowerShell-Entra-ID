<pre lang="markdown">EmailEvents
| where SenderFromAddress == "<user_principle_name>"</pre>
<pre lang="markdown">AuditLogs
| where InitiatedBy['user']['userPrincipalName'] == "<user_principle_name>"</pre>
<pre lang="markdown">SigninLogs
| where "<user_principle_name>"</pre>
<pre lang="markdown">UrlClickEvents
| where AccountUpn == "<user_principle_name>"</pre>
<pre lang="markdown">EmailEvents
| where SenderFromAddress == "<user_principle_name>"</pre>
<pre lang="markdown">search "<user_principle_name>"</pre>
<pre lang="markdown">OfficeActivity
| where UserId == "<user_principle_name>"</pre>
<pre lang="markdown">search "<user_principle_name>"
| summarize by $table
</pre>


<pre lang="markdown">DeviceRegistryEvents
| take 100
| sort by Timestamp desc</pre>

<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
<pre lang="markdown"></pre>
