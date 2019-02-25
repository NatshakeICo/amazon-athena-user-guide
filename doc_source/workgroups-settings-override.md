# Workgroup Settings Override Client\-Side Settings<a name="workgroups-settings-override"></a>

The **Create workgroup** and **Edit workgroup** dialogs have a field titled **Override client\-side settings**\. This field is unselected by default\. Depending on whether you select it, Athena does the following:
+ If **Override client\-side settings** is not selected, workgroup settings are not enforced\. In this case, for all queries that run in this workgroup, Athena uses the clients\-side settings for query results location and encryption\. Each user can specify client\-side settings in the **Settings** menu on the console\. If the client\-side settings are not used, the workgroup\-wide settings apply, but are not enforced\. Also, if you run queries in this workgroup through the API operations, the command line interface, or the JDBC driver, and specify your query results location and encryption there, your queries continue using those settings\.
+ If **Override client\-side settings** is selected, Athena uses the workgroup\-wide settings for query results location and encryption\. It also overrides any other settings that you specified for the query in the console, by using the API operations, or with the driver\. This affects you only if you run queries in this workgroup\. If you do, workgroup settings are used\. 

  If you override client\-side settings, then the next time that you or any workgroup user open the Athena console, the notification dialog box displays, as shown in the following example\. It notifies you that queries in this workgroup use workgroup's settings, and prompts you to acknowledge this change\.  
![\[The screenshot that shows the acknowledgement for the workgroups settings override.\]](http://docs.aws.amazon.com/athena/latest/ug/images/wg-settings-override-acknowledge.png)
**Important**  
If you run queries through the API operations, the command line interface, or the JDBC driver, and have not updated your settings to match those of the workgroup, your queries run, but use the workgroup's settings\. For consistency, we recommend that you omit client\-side settings in this case or update your query settings to match the workgroup's settings for the results location and encryption\. To check which settings are used for the workgroup, [view workgroup's details](workgroups-create-update-delete.md#viewing-details-workgroups)\. 