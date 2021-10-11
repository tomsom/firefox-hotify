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

/* MAIN BACKGROUND: */
--bg: #1a1b26;

/* ACCENT */
--accent: #24283b;

/* TEXT ACCENT */
--accent-text: #565f89;

/* PROGRESSBAR BACKGROUND */
--pgb-bg: #565f89;
}

/* HIDE: */
/* -Spotify logo
 * -Install app button
 * -Upgrade button
 * -Account button
 * -Artist and playlist banner */
.D_XKXBZDhgpM1KrmKy3O,
.i0XB7255K_4QFLJsSGc_,
.GGdmQ1RUtuGP7ClED7uf,
.PnXH8Hvc4os3tFpc10_z,
._dsx4Y9jukDHLzhl7bQb.wQi0raQMEJJrELuj_2FP {
   display: none; 
  }

/* set background color */
.Root__top-container,
.LcjM521yr5D14A54HbQl,
.We1fExPHxLIRmV0rZGNo,
.e2JzVB2WkGm7GMT8rkEg,
.EGbXItTF_kUHbao1jeCp,
.iYoKwYJwszPZXYQCZQ4s,
.fynR25MOeILQ7mCZ8247,
.euOnte9wvOF0D_SGxEZ9,
.JBEYL0L5KiIeKcmT3gNp,
.gqeP9Y0_y6DLm4CD_m3Q,
.Root__nav-bar,
.contentSpacing {
  background-image: none;
  background-color: var(--bg);
}

/* set accent colors */
.os-scrollbar-handle,
.KL469QQzoRZLOmKomNzk,
._clplXKRPuAbAoCUarH0,
.OALAQFKvC7XQOVYpklB4,
.pLwpjUDpZgzSXNOsGn_c,
.dIwMadpRrW1PwEwEeAbN,
.CPgTPk9wPOVigmNI6xWP,
.h4DQmL9PpLcsYvf0yGno {
  background: var(--accent) ;
  color:var(--accent-text);
}

/* move sidebar to make place for 
 * back and foreward button */
.Root__nav-bar {
  padding-top: 40px;
  z-index: 0;
}

/* move back and foreward button
 * above sidebar */
.vxv8l5aw6EzrYxBGyQ33 {
  position: fixed;
  top: 20px;
  left: 20px;
}

/* remove top padding main view */
.HiyUdbeEyoMBpq5N84ND {
  padding-top: 0px;
}

/* remove shadow of playlist/album cover */
.XRD1P2qyA9MlnhSLnxwi {
    box-shadow: none;
}


/* PROGRESSBAR MODS: */

/* set progressbar as top border
 * of bottom playback bar */ 
.playback-bar {
  position: fixed;
  bottom: 82px;
  left: 0px;
}

/* set progressbar background */
.DRdf8zxrOUXwYM3zXYRc {  
  background-color: var(--pgb-bg);
}


/* move timestamps to respective
 * position at window border */
.OlJJ1YWOPpopfYVa0E1L,
.X4mdgRzyBsWSX2RQYm_w {
  position: fixed;
  bottom: 64px;
}
.playback-bar__progress-time-elapsed.X4mdgRzyBsWSX2RQYm_w {
  left: 0px !important;
}
.OlJJ1YWOPpopfYVa0E1L {
  right: 0px;
}

/* shrink cover image to allow
 * clearance for left timestamp */ 
.cover-art {
  height: 46px;
  width: 46px ;
  margin-top: 17px;
}

/* fix artist link position */
.GzHNAzm2S2V6B_1vzk03.standalone-ellipsis-one-line.X4mdgRzyBsWSX2RQYm_w {
  bottom: 3px !important;
  left: 60px !important;
}
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
