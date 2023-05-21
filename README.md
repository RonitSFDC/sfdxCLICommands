# sfdxCLICommands
Few useful sfdxCLi commands
// Imagine a world where managing Apex debug logs becomes effortless. No more tedious manual deletions, just a clever trick to save you time and frustration. Let me unveil this hidden gem!
Execute the first command, and like a skilled wizard, it discreetly queries your Salesforce org, capturing the IDs of all those bothersome Apex debug logs. To keep things covert, it gently saves the results in a file named "debuglogs.csv".
sfdx force:data:soql:query -q "SELECT id FROM ApexLog" -r csv > debuglogs.csv
Prepare for the grand finale! The second command, operating behind the scenes, calls upon the mighty Salesforce CLI. It gracefully initiates a stealthy bulk deletion operation, relying on the file you created to perform its vanishing act.
sfdx force:data:bulk:delete -s ApexLog -f debuglogs.csv
