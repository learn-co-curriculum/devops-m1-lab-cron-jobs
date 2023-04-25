# Cron Jobs Lab

## Task

In this lab, we're going to set up a cron job to practice automating tasks.

## Instructions

### Creating the script

Let's go ahead and create a script that will run periodically, feel free to throw it in a folder of your choosing (preferably under your home (~) directory):
 
```bash
$ nano /path/to/cron-lab.sh
```

Save the script including the following code that writes to a file the time during which the command ran:

```bash
#!/bin/bash
echo "Logged date is: $(date)" >> /home/<user>/time_ran.txt
```

> The `>>` operator appends to the end of the file. In this case, every time the script run, it will add a new line with the echo'd message. So if the script runs 10 times, you'll have 10 different lines with the time.

Make sure to replace `<user>` with your your username.

In order for the script to be able to run, we need to make sure it is marked as executable:

```bash
$ chmod +x /path/to/cron-lab.sh
```

### Setting up the cron job

Now we can set up the job itself:

```bash
$ crontab -e 
```

Add the following line to the end of the file to run the cron job every minute:

```bash
* * * * * /path/to/cron-lab.sh
```

Now simply wait a couple of minutes to allow it to write to the `time_ran.txt` file, and check the output:

```bash
$ cat /home/<user>/time_ran.txt
```

## Submission

Take a screenshot of the terminal after running the command `cat /home/<user>/time_ran.txt`, with the output visible:

Upload the screenshot as the submission for this assignment.
