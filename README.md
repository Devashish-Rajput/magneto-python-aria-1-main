# Important - Read these points first:
- Original repo is https://github.com/lzzy12/python-aria-mirror-bot
- I have collected some cool features from various repositories and merged them in one.
- So, credits goes to original repo holder, not to me. I have just collected them.
- This (or any custom) repo is not supported in official bot support group.
- So if you have any issue then check first that issue is in official repo or not, You are only allowed to report that issue in bot support group if that issue is also present in official repo.
- Fork and Deploy !!
	- Don't Deploy to Heroku without forking my Repo ⚠️


## Credits:
- First of all, full credit goes to [Shivam Jha aka lzzy12](https://github.com/lzzy12) He build up this bot from scratch.
- Then a huge thanks to [Sreeraj V R](https://github.com/SVR666) You can checkout his [repo here](https://github.com/SVR666/LoaderX-Bot)
- Features added from [Sreeraj V R's](https://github.com/SVR666) repo -
```
1. Added Inline Buttons
2. Added /del command to delete files from drive
3. /list module will post search result on telegra.ph
```
- Special thanks to [archie](https://github.com/archie9211) for very much useful feature **Unzipmirror**
- Features added from [archie](https://github.com/archie9211)'s repo
```
1. unzipmirror
2. Update tracker list dynamically
3. Fix SSL handsake error
```


# What is this repo about?
This is a telegram bot writen in python for mirroring files on the internet to our beloved Google Drive.


# Inspiration 
This project is heavily inspired from @out386's telegram bot which is written in JS.


# Features supported:
- Mirroring direct download links to google drive
- Mirroring Mega.nz links to google drive (In development stage)
- Mirror Telegram files to google drive
- Mirror all youtube-dl supported links
- Extract zip, rar, tar and many supported file types and uploads to google drive
- Copy files from someone's drive to your drive (using Rclone)
- Service account support in cloning and uploading
- Download progress
- Upload progress
- Download/upload speeds and ETAs
- Docker support
- Uploading To Team Drives
- Index Link support


## New ChangeLog by [@AbirHasan2005](https://github.com/AbirHasan2005):
- New code in Line 14 of requirements.txt file.
	- As you know one of the most popular YouTube video downloading software, **youtube-dl**, was removed from GitHub, according to a release from the **Recording Industry Association of America (RIAA)**.
	- New code working well.

- Improvements in Dockerfile.
        - Before Deploy edit Dockerfile. To know what you have to edit ask in Telegram Group: [Linux Repositories](https://t.me/linux_repo)

- You have to change Deploy Button link with your forked Repo Link.
        - For help Ask in Telegram Group: [Linux Repositories](http://t.me/linux_repo)

## About Mega.nz links Mirroring:
As you know mega.nz links mirroring is on Development Stage. So there are a lot of bugs. Bot can crash and Restart it self automatically. Do mega.nz Mirroring at your own risk.


## Bot commands to be set in BotFather

```
mirror - start mirroring
tarmirror - upload tar (zipped) file
unzipmirror - extract files
clone - copy folder to drive
watch - mirror YT-DL support link
tarwatch - mirror youtube playlist link as tar
cancel - cancel a task
cancelall - cancel all tasks
del - delete file from drive
list - [query] searches files in G-Drive
status - get mirror status message
stats - bot usage stats
help - get detailed help
ping - ping bot
log - bot log [owner only]
```
You can also change the commands. For help ask in [Telegram Group](https://t.me/linux_repo).


# How to deploy?

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://dashboard.heroku.com/new?template=https://github.com/RAHUL112KAPOOR/magneto-python-aria-1/tree/main)

- Configs [Here](https://github.com/RAHUL112KAPOOR/magneto-python-aria-1/tree/main#configs)
- For any help ask in [Telegram Group](https://t.me/linux_repo):
- <a href="https://t.me/linux_repo"><img src="https://img.shields.io/badge/Telegram-Join%20Telegram%20Group-blue.svg?logo=telegram"></a>

- You can also deploy on VPS !!


### Setting up config file:

`cp config_sample.env config.env`

- Remove the first line saying:
```
_____REMOVE_THIS_LINE_____=True
```
Fill up rest of the fields. Meaning of each fields are discussed below:

# Configs:
- **BOT_TOKEN** : The telegram bot token that you get from [@BotFather](https//t.me/BotFather)
- **GDRIVE_FOLDER_ID** : This is the folder ID of the Google Drive Folder to which you want to upload all the mirrors.
- **DOWNLOAD_DIR** : The path to the local folder where the downloads should be downloaded to. For Heroku put `/app/downloads`
- **DOWNLOAD_STATUS_UPDATE_INTERVAL** : A short interval of time in seconds after which the Mirror progress message is updated. (I recommend to keep it 5 seconds at least).
- **OWNER_ID** : The Telegram user ID (not username) of the owner of the bot.
- **AUTO_DELETE_MESSAGE_DURATION** : Interval of time (in seconds), after which the bot deletes it's message (and command message) which is expected to be viewed instantly. Note: Set to `-1` to never automatically delete messages.
- **IS_TEAM_DRIVE** : (Optional field) Set to `True` if **GDRIVE_FOLDER_ID** is from a Team Drive else False or Leave it empty.
- **USE_SERVICE_ACCOUNTS**: (Optional field) (Leave empty if unsure) Whether to use service accounts or not. For this to work see "Using service accounts" section below.
- **INDEX_URL** : (Optional field) Refer to https://github.com/maple3142/GDIndex/ The URL should not have any trailing '/'
- **API_KEY** : This is to authenticate to your telegram account for downloading Telegram files. You can get this from https://my.telegram.org DO NOT put this in quotes.
- **API_HASH** : This is to authenticate to your telegram account for downloading Telegram files. You can get this from https://my.telegram.org

- **TELEGRAPH_TOKEN** : Telegraph token generated by running:
        
        python3 generate_telegraph_token.py
	- Or Run in [Repl.it](https://telegraph-token.sonywegas.repl.run)

- **USER_SESSION_STRING** : Session string generated by running:

        python3 generate_string_session.py
	- Or Run in [Repl.it](https://string-session.sonywegas.repl.run)

- **MEGA_API_KEY**: Mega.nz API key to mirror mega.nz links. Get it from [Mega SDK Page](https://mega.nz/sdk).
- **MEGA_EMAIL_ID**: Your Email ID you used to sign up on mega.nz for using premium accounts (Leave th).
- **MEGA_PASSWORD**: Your password for your mega.nz account.
- **STOP_DUPLICATE_MIRROR**: (Optional field) (Leave empty if unsure) if this field is set to `True`, bot will check file in drive, if it is present in drive, downloading will be stopped. (Note - File will be checked using filename, not using filehash, so this feature is not perfect yet)
Note: You can limit maximum concurrent downloads by changing the value of MAX_CONCURRENT_DOWNLOADS in aria.sh. By default, it's set to 2

## Auto Authorize Chat or User:
Add Group IDs or User IDs on [authorized_chats.txt](https://github.com/AbirHasan2005/magneto-python-aria)
- One ID Per Line
- That could be Group ID or User ID

## Getting Google OAuth API credential file

- Visit the [Google Cloud Console](https://console.developers.google.com/apis/credentials)
- Go to the **OAuth Consent Screen** tab, fill it, and save.
- Go to the **Credentials** tab and click **Create Credentials** -> **OAuth Client ID**
- Choose **Desktop** and Create.
- Use the download button to download your credentials.
- Move that file to the root of mirror-bot, and rename it to `credentials.json`
- Visit [Google API page](https://console.developers.google.com/apis/library)
- Search for `Drive` and enable it if it is disabled
- Finally, run the script to generate token file `token.pickle` for Google Drive:

        pip install google-api-python-client google-auth-httplib2 google-auth-oauthlib
        python3 generate_drive_token.py
	- Or run in [Repl.it](https://gdrive-token.sonywegas.repl.run)


## Using service accounts for uploading to avoid user rate limit
For Service Account to work, you must set **USE_SERVICE_ACCOUNTS**="True" in config file or environment variables
Many thanks to [AutoRClone](https://github.com/xyou365/AutoRclone) for the scripts
## Generating service accounts
Step 1. Generate service accounts [What is service account](https://cloud.google.com/iam/docs/service-accounts)
---------------------------------
Let us create only the service accounts that we need. 
**Warning:** abuse of this feature is not the aim of autorclone and we do **NOT** recommend that you make a lot of projects, just one project and 100 SA allow you plenty of use, its also possible that overabuse might get your projects banned by Google. 

```
Note: 1 service account can copy around 750gb a day, 1 project makes 100 service accounts so thats 75tb a day, for most users this should easily suffice. 
```

```
python3 gen_sa_accounts.py --quick-setup 1 --new-only
```

A folder named accounts will be created which will contain keys for the service accounts created.

NOTE: If you have created SAs in past from this script, you can also just re download the keys by running:
```
python3 gen_sa_accounts.py --download-keys project_id
```

### Add all the service accounts to the Team Drive or folder
- Run:
```
python3 add_to_team_drive.py -d SharedTeamDriveSrcID
```

## Youtube-dl authentication using `.netrc` file
For using your premium accounts in youtube-dl, edit the netrc file (in the root directory of this repository) according to following format:
```
machine host login username password my_youtube_password
```
where host is the name of extractor (eg. youtube, twitch). Multiple accounts of different hosts can be added each separated by a new line


### For any kind of help ask in [Telegram Group](https://t.me/linux_repo):
<a href="https://t.me/linux_repo"><img src="https://img.shields.io/badge/Telegram-Join%20Telegram%20Group-blue.svg?logo=telegram"></a>
