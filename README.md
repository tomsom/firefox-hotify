# firefox-hotify
###### Make the spotify webplayer more modern, stealthy and change up the colors

## Content:
* [How it works](#how-it-works)
* [What it looks like](#what-it-looks-like)
* ['Installation':](#installation)
  * [1. Install Stylebot by Ankit Ahuja](#1-install-stylebot-by-ankit-ahuja)
  * [2. Add CSS to Stylebot](#2-add-css-to-stylebot)
  * [3. Basic configuration](#3-basic-configuration)
* [Modify browser as a Spotify app replacement](#modify-browser-as-a-spotify-app-replacement)
  * [1. Set Spotify as browser homepage](#1-set-spotify-as-browser-homepage)
  * [2. Remove tabs and toolbar](#2-remove-tabs-and-toolbar)
  * [3. Add it as a desktop entry](#3-add-it-as-an-desktop-entry-to-show-up-in-an-app-launcher-etc)
  
## How it works:
- Add the stylebot extention
- Add a few lines of CSS to stylebot
- Remove tabs and toolbar of the browser (optional)

## What it looks like:
- Remove (un-)necessary stuff
- Change most of the colors
- Switch up the player controls


![Screenshot_2021-10-10 Spotify - Web Player Music for everyone](https://user-images.githubusercontent.com/50613331/136693789-73de1cae-27c2-4f77-bfef-e74f546b1c8b.png)
![Screenshot_2021-10-10 Spotify - Web Player Music for everyone(4)](https://user-images.githubusercontent.com/50613331/136693834-dae977ce-6b83-4f3f-b483-0ba0a4dfc3cd.png)

### Before:
![Screenshot_2021-10-10 Spotify - Web Player Music for everyone(2)](https://user-images.githubusercontent.com/50613331/136693840-cc72f876-fb67-48f6-bf29-492b0f256f28.png)

## 'Installation':

### 1. Install Stylebot by Ankit Ahuja
Follow the link and install the extention for your browser:
- [Firefox](https://addons.mozilla.org/en-US/firefox/addon/stylebot-web/)
- [Chrome(-ium)](https://chrome.google.com/webstore/detail/stylebot/oiaejidbmkiecgbjeifoejpgmdaleoha)
- [Stylebot website](https://stylebot.dev/)

You might also want to install [uBlock Origin](https://ublockorigin.com/) ;)

### 2. Add CSS to Stylebot
Once installed go to the [Spotify Webplayer Page](https:open.spotify.com) and click on the stylebot extention icon in the toolbar(might be hidden in an overflow menu).

&#8594; Open Stylebot

&#8594; Click in the 'Code' tab

&#8594; Insert the following CSS

```
/* COLORS: */
    body {
    /* main background and shades */
        --bg: #1a1b26;
        --bga: #1a1b2677;
        --bga2: #1a1b2644;

    /* accent colors */
        --accent: #24283b;

    /* text accent*/
        --accent-text: #565f89;
    }
    .TywOcKZEqNynWecCiATc {
    /* progessbar(playback/volume) colors: */
        /* background */
        --bg-color: var(--accent);
        /* foregrounf */
        --fg-color: var(--accent-text);
        /* on hover */
        --is-active-fg-color: white;
    }


/* HIDE: */
    /* Spotify logo */
    /*.NyIynkmMpZXSoaE3XGhA,*/

    /* Upgrade button */
    .Qt5xfSWikz6CLU8Vobxs,

    /* Install app button */
    .WvLkmOVB2R2vzI2ibR_r,

    /* weird shadow in sidebar */
    .GABF6hN5nVeGNtN8vb_q {
        display: none; }


/* CHANGE BACKGROUND: */
    /* main view */
    .Root__main-view,
        /* >playlist bg */
        .rezqw3Q4OEPB1m4rmwfw,
        /* >playlist row header bg */
        .qJOhHoRcFhHJpEQ2CwFT.koyeY6AgGRPmyPITi7yO,
        /*  >genre pages bg */
        .Ft1cMGlqDsCbqmXQyeKN,

    /* sidebar */
    .Root__nav-bar,

    /* now playing bar */
    footer {
        background-color: var(--bg); }


/* SECONDARY COLORS */
    /* back/foreward buttons */
    .VgSbatGBB9XwTH2_dsxg .ql0zZd7giPXSnPg75NR0,

    /* account button and popup*/
    .odcjv30UQnjaTv4sylc0,
    .SboKmDrCTZng7t4EgNoM,

    /* home - cards */
    .LunqxlFIupJw_Dkx6mNx,

    /* search pill */
    .QO9loc33XC50mMRUCIvf {
        background-color: var(--accent); }


/* MAIN PLAY BUTTON */
    .A8NeSZBojOQuVvK4l1pS {
        background-color: var(--accent-text);}
    .A8NeSZBojOQuVvK4l1pS > svg:nth-child(1) {
        fill: var(--bg)}


/* FIXING TEXTS */
    /* search pill text/foreground */
    .QO9loc33XC50mMRUCIvf,
    .hDgDGI,

    /* current song title */
    .y9ohL21kdZwx3S9EuDh2,

    /* playback time */
    .SYnLm8pwZls9sOX9AvJZ {
        color: var(--accent-text);
        fill: var(--accent-text) }


/* FIXING THE GRADIENTS */
    /* home-greeter gradient */
    .vzMSLXDXM8yiYziBe_UK {
        background-image: linear-gradient(rgba(0,0,0,.6) 0, var(--bg)); }

    /* home-greeter cards background */
    .Z35BWOA10YGn5uc9YgAp {
        background-color: var(--bga2); }

    /* playlist-banner gradient */
    .xYgjMpAjE5XT05aRIezb {
        background: linear-gradient(transparent 0,var(--bga)); }
    .uebZpDr3EwDvpO0w6P9U {
        background-image: linear-gradient(var(--bga) , var(--bg)); }
```

### 3. Basic configuration:
- Feel free to change the colors by modifying the variables at top(the default colors a based on the [tokio night vsc theme](https://github.com/enkia/tokyo-night-vscode-theme))
- Hidden elements you might want to be shown can be readded by deleting or commenting the class names from the hide-list below the color variables(the order of the class names is the same as in the comment above it)
- If you want to revert to the default progressbar delete or comment everything below ```/* PROGRESSBAR MODS: */```

## Modify browser as a Spotify app replacement
Note: This configurtion will make your browser unsuitable for normal use. If you use Firefox as your main browser consider using another Firefox based browser (like Waterfox, Librewolf etc.) for this.

### 1. Set Spotify as browser homepage:
&#8594; Firefox Settings &#8594; Home &#8594; Custom URLs... &#8594; Enter: ```"https://open.spotify.com"```

### 2. Remove tabs and toolbar:
- Depending on your OS go to:
  - Linux: ```~/.mozilla/firefox/```
  - OS X: ```Users/<username>/Library/Application Support/Firefox/```
  - Windows: ```C:\Users\<username>\AppData\Roaming\Mozilla\Firefox\```
- Enter the folder ending with '.default-release'
- Create a folder named 'chrome' if not existant already
- In there create a file named userChrome.css and add the following to it:
userChrome.css:
  ```
  /* REMOVE TOOLBAR */
  #nav-bar {
    visibility: collapse;
  }

  /* REMOVE TAB'S BAR */
  #TabsToolbar .toolbar-items {
    display: none !important;
  }
  ```
  To add tabs and toolbar again simply remove the CSS above from the userChrome.css file.
  
  ### 3. Add it as a desktop entry (to show up in an app launcher etc.)
  - Linux:
    - ```nano ~/.local/share/applications/hotify.desktop```
    - Paste
```
[Desktop Entry]
Encoding=UTF-8
Version=1.0
Type=Application
Terminal=false
Exec=/usr/bin/firefox
Name=Hotify
Icon=/path/to/icon
```
You might also want to add an icon: Download e.g. [here](https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/1024px-Spotify_logo_without_text.svg.png) and adjust the path in the .desktop file accordingly.

- Windows:
  - Change the icon and name of Firefox desktop link
  - Get icon e.g. [here](https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/1024px-Spotify_logo_without_text.svg.png) and export it as .ico in GIMP

## DONE!
