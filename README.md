# Using This Repository

Chances are you do not work in exactly the same way as I do. I use Vim (find my 
[.vimrc here](https://github.com/tgrosinger/dotfiles/blob/master/.vimrc)) as my primary editor, 
and generally program in either Go or Python. The commands and grammars that 
are shared in this repository reflect that and are designed to work in my 
workflow.

That said, the grammars found here should be a good starting point either as
examples or templates to help you write your own. It takes a while, but if they
are built up over time I have found they can be very powerful.

## Contributing

Want to help make getting started with voice coding easier? Send me a pull 
request! 

I would love to add more languages and more features. There are plenty 
of commands that are missing, and even more that not work as well as they could. 
Any help is welcome.

And of course if you have a friend who struggles with RSI or carpal tunnel 
syndrome please tell them there is a better way.

# Installation instructions

## Client

These steps are meant to be performed on a Windows machine with an attached
microphone. I suggest using a virtual machine as it will allow you to save
snapshots as you progress through the steps.

The machine should have about 2GB of ram and two processors.

1. Install [Dragon NaturallySpeaking 13.0](http://www.nuance.com/for-individuals/by-product/dragon-for-pc/index.htm) to default location
2. Take a snapshot of the VM
3. Download and install [Python 2.7.8 for x32](https://www.python.org/downloads/windows/)
4. Run [get-pip.py](https://bootstrap.pypa.io/get-pip.py) to install pip
5. Install the latest release of [pywin32 for Python 2.7](http://sourceforge.net/projects/pywin32/)
6. Install the latest release of [NatLink](http://sourceforge.net/projects/natlink/)
7. Install other dependencies (`python -m pip install dragonfly jsonrpclib pyparsing`)
8. Take another snapshot of the VM
9. Start a cmd window as administrator
10. Navigate to `C:\NatLink\NatLink\confignatlinkvocolaunimacro`
11. Run `start_natlinkconfigfunctions.py` then use the `e` option to enable
12. If problems are encountered, take a look at [this Github](https://github.com/simianhacker/code-by-voice/issues/2) issue for help
13. Copy `aenea/aenea.json.example` to `C:\NatLink\NatLink\MacroSystem` and edit the ip to the ip of the host
14. Copy the dictation client from the client directory to the NatLink directory
15. Disable the dictation window in Dragon so you can use the dictation client

## Server

These instructions were written for an machine running ubuntu 14.04 LTS.

1. Go to the server (linux machine) and navigate in the aenea dir to `server/linux_x11`
2. Copy `config.py.example` to `config.py` and edit, setting the ip to 0.0.0.0
3. Install pip on the host machine (`sudo apt-get install python-pip`)
4. Install xsel and xdotool (`sudo apt-get install xsel xdotool`)
5. Use pip to install jsonrpclib, and yapsy (`sudo pip install jsonrpclib yapsy`)

## Starting everything.

1. On the server, start `aenea/server/linux_x11/server_x11.py`
2. On the client, start Dragon Naturally Speaking
3. On the client, start `aenea_client.py`
4. Give the dictation window focus so it captures anything not covered by a grammar

## Microphone recommendations

I am using the Yeti by Blue and have found it to perform very well in quiet
environments, but it does have some trouble as the noise level increases or
others start speaking. The on-mic mute button is a very nice feature.
