# Crontab Mac OSx

This is a very simple tutorial (for beginners) that will allow you to understand the basic way of how contrab works in OSX. Since OSx is based in UNIX and always will be, if you are familiar with Linux this will be straightforward to follow.

I am using OS X Yosemite 10.10.5. (This is only for reference, since it is no so relevant).

Here we go!

## What is a schedule job and when I need it?

Have you ever wondered if the script you are writing right now can be executed by itself during a period of time or everyday? 

If you do, the answer is yes, you can do it. Operating System can do it for you, but you have to tell them how to do so, the term used to describe this is "Schedule jobs", and you have to define every job.

Well, maybe it can not be executed by itself but you can tell to your machine to do it for you a certain time. Very similar when you program your alarm to wake up every morning at 6am.

## How it works?

OSx has "crontab", crontab is a command that allows you to get permissions to the system administration and send request to CRON, only Administrator have access to it. The cron is a "daemon" (a long-running background process that answers requests for services). There is only one crontab file and you can use that command to edit it.

## An example: Data weekly update 

1. The script: For this example I will execute a php script to update a table in a database (for now on called **script.php**, I will not give a lot of details about my script because this tutorial is focus on crontab only). 

2.  Execute the command **crontab -e** in your terminal to open the job list (crontab file), you can use your favorite texteditor, in my case i prefer nano while working in the terminal. This will open a file. 

![](https://drive.google.com/file/d/0B-_AwuYBT6-XMF9RVFEyVFFqa0k/view?usp=sharing)
Note: Be aware about the path of your crontab file (Do not forget where it is for future editing).

2.For nano, press  CTRL+O (edit)
What you have to edit after open the file and How a job setting looks like:
I use curl here, to make the apache server run my script (like if you are do it from the browser). 

    *    *    *    *    *    /usr/bin/curl    --silent    http://localhost:8888/bigdata/script.php

Every star represents:   
    Minute | Hour | Day of Month | Month | Day of Week | curl | curl args

This mean this will be execute every day. Please remember that you need to type a tab after every star and sentence.

In the picture below, the script.php will be executed everyday at 12am

Press CTRL+X to save and exit. 

3.If the syntax has no mistakes, you will receive a notification that a new crontab has been installed.

4. After the script has been executed you will receive an email.

That's all.

For more details you can visit this pages that I use for reference.

 * https://kb.iu.edu/d/afiz
 * https://kb.iu.edu/d/aiau
 * https://ole.michelsen.dk/blog/schedule-jobs-with-crontab-on-mac-osx.html
 * https://superuser.com/questions/1144910/how-do-i-setup-a-cron-job-on-os-x-to-run-a-curl-command-at-a-specific-time-every


