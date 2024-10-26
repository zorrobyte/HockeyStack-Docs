# What object/integration is this field pulling from?

To find out what object or integration a field is pulling from, you can:

1. Create a new empty report
2. Add 3 breakdowns: Action Name, Integration, and the field you are analyzing (Both action name and integration are under Action Properties)
3. Click on the field you are analyzing in the breakdowns, click Filter, and filter to "is not empty”
    
    ![Screenshot 2024-09-18 at 4.06.12 PM.png](What%20object%20integration%20is%20this%20field%20pulling%20from%20105f0197a5558093a115fa29de631dd7/Screenshot_2024-09-18_at_4.06.12_PM.png)
    
4. Click on the field you are analyzing in the breakdowns, click Customize, and map all rows that are "not empty” to a text like "Is not empty”
    
    ![Screenshot 2024-09-18 at 4.07.10 PM.png](What%20object%20integration%20is%20this%20field%20pulling%20from%20105f0197a5558093a115fa29de631dd7/Screenshot_2024-09-18_at_4.07.10_PM.png)
    
5. Make sure your columns have Any Action - Times Done
    
    ![Screenshot 2024-09-18 at 4.07.37 PM.png](What%20object%20integration%20is%20this%20field%20pulling%20from%20105f0197a5558093a115fa29de631dd7/Screenshot_2024-09-18_at_4.07.37_PM.png)
    
6. Make sure your date range is "All Times”
7. Click “Preview”

The end result looks like below:

![Screenshot 2024-09-18 at 4.08.43 PM.png](What%20object%20integration%20is%20this%20field%20pulling%20from%20105f0197a5558093a115fa29de631dd7/Screenshot_2024-09-18_at_4.08.43_PM.png)

In this case it looks like the field is being pulled  from Lead, Contact, and CampaignMember objects.