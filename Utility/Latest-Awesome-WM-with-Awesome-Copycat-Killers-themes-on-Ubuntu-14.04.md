Mon Jan 23 13:38:16 PST 2023
Mon Jan 23 13:38:16 PST 2023
##Download Crouton

Download Crouton in the usual way.

##Install Ubuntu 14.04 with X11

In order to get the latest version of Awesome WM working you must use Ubuntu 14.04 LTS with X11 support. To install this:

Press
 
    CTRL-ALT-T

Type

    shell
    sudo sh ~/Downloads/crouton -r trusty -t x11

Allow the installation to finish, add your username and password for Ubuntu.

##Configure Locale/Language

Then you need to configure your language and locale in order for the Copycat-Killers Awesome WM themes to work. I'm UK based so the commands I issue are:

    sudo enter-chroot
    sudo apt-get install language-pack-en
    sudo update-locale LANG="en_GB.UTF-8" LANGUAGE="en:en"

Refer to this page for more instructions on configuring languages:

https://github.com/dnschneid/crouton/wiki/Languages

##Install required packages

Next we need to add a few packages required by Awesome WM and copycat-killers themes:

    sudo apt-get install unclutter nitrogen rxvt-unicode-256color fonts-inconsolata software-properties-common curl imagemagick

##Configure rxvt (not strictly necessary)

Next configure rxvt (a new terminal app) - you do this by adding a .Xdefaults file into your home dir. I've included mine below for reference - it's used with the inconsolata font, font-size 18px (1080p screen - try 11-14 on a 1366x768) with the solarized dark colour scheme:
 
    urxvt*font: xft:Inconsolata:pixelsize=18
    URxvt*scrollBar: false
    URxvt.saveLines: 32767
    URxvt*termName: rxvt

    !! drop in Solarized colorscheme for Xresources/Xdefaults

    !!SOLARIZED HEX     16/8 TERMCOL  XTERM/HEX   L*A*B      RGB         HSB
    !!--------- ------- ---- -------  ----------- ---------- ----------- -----------
    !!base03    #002b36  8/4 brblack  234 #1c1c1c 15 -12 -12   0  43  54 193 100  21
    !!base02    #073642  0/4 black    235 #262626 20 -12 -12   7  54  66 192  90  26
    !!base01    #586e75 10/7 brgreen  240 #585858 45 -07 -07  88 110 117 194  25  46
    !!base00    #657b83 11/7 bryellow 241 #626262 50 -07 -07 101 123 131 195  23  51
    !!base0     #839496 12/6 brblue   244 #808080 60 -06 -03 131 148 150 186  13  59
    !!base1     #93a1a1 14/4 brcyan   245 #8a8a8a 65 -05 -02 147 161 161 180   9  63
    !!base2     #eee8d5  7/7 white    254 #e4e4e4 92 -00  10 238 232 213  44  11  93
    !!base3     #fdf6e3 15/7 brwhite  230 #ffffd7 97  00  10 253 246 227  44  10  99
    !!yellow    #b58900  3/3 yellow   136 #af8700 60  10  65 181 137   0  45 100  71
    !!orange    #cb4b16  9/3 brred    166 #d75f00 50  50  55 203  75  22  18  89  80
    !!red       #dc322f  1/1 red      160 #d70000 50  65  45 220  50  47   1  79  86
    !!magenta   #d33682  5/5 magenta  125 #af005f 50  65 -05 211  54 130 331  74  83
    !!violet    #6c71c4 13/5 brmagenta 61 #5f5faf 50  15 -45 108 113 196 237  45  77
    !!blue      #268bd2  4/4 blue      33 #0087ff 55 -10 -45  38 139 210 205  82  82
    !!cyan      #2aa198  6/6 cyan      37 #00afaf 60 -35 -05  42 161 152 175  74  63
    !!green     #859900  2/2 green     64 #5f8700 60 -20  65 133 153   0  68 100  60

    #define S_base03        #002b36
    #define S_base02        #073642
    #define S_base01        #586e75
    #define S_base00        #657b83
    #define S_base0         #839496
    #define S_base1         #93a1a1
    #define S_base2         #eee8d5
    #define S_base3         #fdf6e3
    #define S_yellow        #b58900
    #define S_orange        #cb4b16
    #define S_red           #dc322f
    #define S_magenta       #d33682
    #define S_violet        #6c71c4
    #define S_blue          #268bd2
    #define S_cyan          #2aa198
    #define S_green         #859900

    *background:            #002b36
    *foreground:            #657b83
    *cursorColor:           #93a1a1
    *pointerColorBackground:#586e75
    *pointerColorForeground:#93a1a1

    !! black dark/light
    *color0:                #839496
    *color8:                #002b36

    !! red dark/light
    *color1:                #dc71c4
    *color9:                #cb4b16

    !! green dark/light
    *color2:                #859900
    *color10:               #586e75

    !! yellow dark/light
    *color3:                #b58900
    *color11:               #657b83

    !! blue dark/light
    *color4:                #268bd2
    *color12:               #839496

    !! magenta dark/light
    *color5:                #d33682
    *color13:               #6c71c4

    !! cyan dark/light
    *color6:                #2aa198
    *color14:               #93a1a1

    !! white dark/light
    *color7:                #eee8d5
    *color15:               #fdf6e3


There are a couple of ways to add the .Xdefaults file - the easiest is to add the Text text editor to Chrome OS, copy and paste the above code into the text edit and save it as .Xdefaults in the Downloads folder. Then from inside the shell do this:

    cp ~/Downloads/.Xdefaults ~/.Xdefaults

##Add the latest version of Awesome WM to apt

Now we need to add a PPA for the most recent version of Awesome WM and update our apt:

    sudo add-apt-repository ppa:klaus-vormweg/awesome
    sudo apt-get update

##Install Awesome WM

Now we can install the latest version of Awesome (currently 3.5.6)

    sudo apt-get install awesome

Check our Awesome version:

    awesome -v

This should say awesome v3.5.6 (For Those About To Rock) - if it does then we've been successful!

Now we just need to add a few extras and pick a Copycat-Killers Awesome theme. First do this:

    echo "exec awesome" > ~/.xinitrc

##Install a Copycat-Killers theme

Now lets install our awesome theme. Do the following:

    sudo apt-get install git

Then do this:

    cd ~/
    git clone https://github.com/copycat-killer/awesome-copycats.git

Take a look at https://github.com/copycat-killer/awesome-copycats to pick your favourite theme.

Copy the contents of awesome-copycats into ~/.config/awesome

To do this:

    mkdir ~/.config/awesome
    cp -r ~/awesome-copycats ~/.config/awesome

Then activate your favourite awesome copycat theme:

    cp ~/.config/awesome/rc.lua.copland ~/.config/awesome/rc.lua

Note: Change copland to whatever your favourite theme is. 

##Start up Ubuntu with Awesome WM

You should be ready to fire up Awesome WM! Type exit to leave the chroot then:

    sudo enter-chroot xinit

And check if its all worked!

Press Search + Enter to bring up a terminal and start installing anything and everything you'd like. I went for Chrome, Sublime Text 3, Thunderbird and Skype. Makes for a cheap and amazing full stack developer IDE once you start customising it to your needs.

All credit should go to Isaac Pei for his original guide on installing Awesome in Crouton.

##Optional/Useful Extras

Here are some useful extra commands which can be run from terminal each time you start or added to a startup script:

    setxkbmap gb (changes the default keyboard layout to British)
    synclient VertScrollDelta=-111 (changes scroll direction to Australian scrolling)
    syndaemon -i 0.25 -K -d (prevents use of the trackpad for a quarter of a second after you stop typing)

You can also add in functionality like a delete key option using xkeybinds and xvkbd. 

To do this, install the following:

    sudo apt-get install xvkbd

Then create a .xkeybinds file in your home dir and put this inside it:

    #Delete
    "xvkbd -xsendevent -text '\[Delete]'"
    m:0x40 + c:22
    Mod4 + BackSpace
    
    #
    # End of xbindkeys configuration

This turns Search+Backspace into a delete key.

Once you've saved your .xkeybinds - run this command:

    xkeybinds  