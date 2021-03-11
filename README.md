# How-To-Host-On-Repl

# Step 1
Go to https://repl.it/ and login

# Step 2
Create a new 'Node.js' repl, the name can be whatever you'd like

# Step 3
Go to the 'Shell' tab in the console and type the following commands
```
git clone <URL>.git
mv ./<NEW FOLDER GENERATED>/* ./
rm ./<NEW FOLDER GENERATED> -f -r -d -v
clear
```
# Step 4
Refresh and then run the system using the Run button at the top of the repl

If you're getting an error saying that it can't find a directory, make sure that there's a directory (folder) called '.data' with a file called 'db.sqlite', if there's not, then create a folder called '.data' and create a file in that folder called 'db.sqlite'

# Step 5
If you saw a white window pop up after you ran it, skip this part, if you didn't continue

Now that we've successfully gotten the repl booted up, time to make it a webserver!

Please paste the following code at the top of index.js
```js
const express = require('express');
const app = express();
app.get('/', async (request, response) => {
     response.sendStatus(200);
});
let listener = app.listen(process.env.PORT, () => {
    console.log(`Your app is currently listening on port: ${listener.address().port}`);
});
```
And then Reboot

# Step 6
Go to https://uptimerobot.com/ and login

# Step 7
Add a new monitor with the following settings
```
Type: HTTP(S)
Name: <Anything that you want>
IP: The repl URL (hint: it ends with .co)
Interval: 5 minutes
```
# Step 8
Enjoy!
