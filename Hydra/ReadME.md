# Hydra {TRY HACK ME}

![Room Image](https://github.com/M4ddy19/TRYHACKME-Writeups/blob/main/Hydra/Images/Room.png)

We are asked to bruteforce molly's web and ssh password and get the flags using the credentials.

First let's open the web page.

![WebPage](https://github.com/M4ddy19/TRYHACKME-Writeups/blob/main/Hydra/Images/1.png)

Now we have to check for the request method.

To check the request method open developer tools (Ctrl + Shift + I)  and select network option. Now fill login details with any username and password and click on login. Then select login in developer tools and we will get the request method. This time request method is POST.

![Request Method](https://github.com/M4ddy19/TRYHACKME-Writeups/blob/main/Hydra/Images/2.png)

Now let's bruteforce it

> hydra -l molly -P /PATH TO WORDLIST  {MACHINE IP}  http-post-form  "/login:username=^USER^&password=^PASS^:F=incorrect" -VV

![web bruteforce](https://github.com/M4ddy19/TRYHACKME-Writeups/blob/main/Hydra/Images/3.png)

And we got the password

Now login using this password on web and we will get the flag1.

![flag1](https://github.com/M4ddy19/TRYHACKME-Writeups/blob/main/Hydra/Images/4.png)

Q) Use Hydra to bruteforce molly's web password. What is flag 1?
A) THM{*********************************}

Let's now bruteforce the ssh password

> hydra -l molly -P /PATH TO WORDLIST ssh://{MACHINE IP}

![ssh bruteforce](https://github.com/M4ddy19/TRYHACKME-Writeups/blob/main/Hydra/Images/5.png)

We got the ssh password, now login to machine using this password and get the flag2

ssh molly@{MACHINE IP}

![flag2](https://github.com/M4ddy19/TRYHACKME-Writeups/blob/main/Hydra/Images/6.png)

Q) Use Hydra to bruteforce molly's SSH password. What is flag 2?
A) THM{*********************************}
