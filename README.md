# Newegg Shuffle
Python module(s) to help you with the Newegg raffle

# How to use
```
$ git clone https://github.com/Matthew17-21/Newegg-Shuffle
$ cd Newegg-Shuffle
$ pip3 install -r requirements.txt
$ python3 main.py
```
- **Checkout the [file structure](https://github.com/Matthew17-21/Newegg-Shuffle#file-structure) below on how to enter & change data**

# File Structure
### /data
- emails.txt
    * Enter the emails you'd like to create accounts for.
- proxies.txt
    * Proxies that'll be used when creating accounts.
- settings.json

| Key | Type | Description | Options |
| :--:| :---:| :---------: | :-----: |
| output_filename | String | File name where the sessions will be saved | - |
| version | String | Type of captcha you want to solve to create the account | v2 or v3 |
| captcha_solver | String or int | Captcha solving site | Checkout the [documentation.](https://github.com/Matthew17-21/Captcha-Tools#how-to-use) |
| keys | dict | dict containing keys to solving sites | - |
| generate_random | bool | Should the program generate random password. | `true` or `false` |
| choices | array | Array of password choices | - |


### /newegg/*
- Contains the core software code. 

# Recommendations
1. **MAKE SURE YOU STORE YOUR SESSIONS SOMEWHERE**
2. Althought not completely necessary, but you should add/delete/randomify events for accertify.
3. Make sure iOS app version is up to date
4. Handle exceptions better
    * There are some exceptions, such as those from [captchatools](https://github.com/Matthew17-21/Captcha-Tools#exceptions), that I did not handle.
5. Use proxies (But they aren't required to run the script)
6. If V2 Recaptcha pops up again, use that over V3


# Notes
- Failed captchas are normal.
- Newegg disabled their V2 Recaptcha for creating accounts, making V3 the only option. Because all 3rd party solvers aren't the best at V3 captchas, there will be lots of failed captchas.
    * I recommend using anticaptcha for V3, but Capmonster & 2Captcha is also available.
- Only tested on Python 3.7
    * *Should* work on other versions, but I can't promise anything.
- This is intended for devs, so try not to change too much code as it might break something.
- This isn't a reflection of how I actually write code so pls don't judge too hard :joy:
    * I've been writing in Go lately, hence the structure of the whole thing.
- If you want to create accounts via mobile, change line 79 in `main.py` from `desktop.Create_Account(self, email)` to `mobile.Create_Account(self, email)`
    * And vice versa 
- There are lots of ways to make this better, cleaner and better on memory. If I find till I'll update this repo.

# FAQ
1. Does this work out of the box?
    * Yes, however, you do need change some info.
2. Can I use these accounts for the raffle?
    * Yes.
3. Should I use the mobile or desktop module?
    * Use the same mode you'll be using to enter raffles.
        * Entering raffle via app, use the mobile version to create account.
        * Entering raffle via desktop, use the desktop version to create account.
4. How do I use the captchatools?
    * Checkout the [documentation.](https://github.com/Matthew17-21/Captcha-Tools)

# Success
![Genning](https://i.imgur.com/lvrTp36.png)
![Success](https://i.imgur.com/8csUoqR.png)

# TO DO 
1. [] Clean up code
2. [] Update documentation
