# Testing the website tracking script

1. Navigate to the domain where the script was added. Turn off your adblocker, and make sure to accept cookies.
2. Right click on the page > Inspect Element.
3. Navigate to the elements tab, click anywhere on the code, and on your keyboard click Cmd+F  (or Ctrl+F for Windows) to search for “hockeystack.min.js”. Validate that you can find the below snippet.
    
    ![Screenshot 2024-03-29 at 16.58.48.png](Testing%20the%20website%20tracking%20script%20a9b946de21fc454e99ec2ae385bca4de/Screenshot_2024-03-29_at_16.58.48.png)
    
4. As a secondary check, navigate to the Network tab. Refresh the page while you are on the tab. On the input box where it says “Filter”, enter in “hockeystack”. Make sure you can see a line where Name is “send” and Status is 200.
    
    ![Screenshot 2024-03-29 at 17.00.17.png](Testing%20the%20website%20tracking%20script%20a9b946de21fc454e99ec2ae385bca4de/Screenshot_2024-03-29_at_17.00.17.png)
    

If both checks are passing — Congrats! Your HockeyStack script is working!