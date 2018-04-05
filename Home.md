## Introduction

This guide is for the beginner oUF layout creator. It aims to demostrate how to use oUF in a structured step-by-step way.

#### Prerequisites
  1. You are familiar with the Lua 5.1 basics ([The Lua 5.1 Reference Manual](https://www.lua.org/manual/5.1/)).
  2. You know how to create a simple addon ([Getting started with writing addons](https://wow.gamepedia.com/Getting_started_with_writing_addons)).
  3. Some knowledge in _git_ is a plus ([The Git Book](https://git-scm.com/book/en/v2)).

If you lack knowledge on the first two topics of this list, then this guide is not for you.
Knowing _git_ might be helpful as it makes it possible to create separate branches for your changes and you can easily restore your local copy of the repository to a known good state if something goes wrong.

#### How to use this guide

The basic intent is for you to follow the commits from start to end and try to recreate them yourself. Feel free to change the code on the go to get a better understanding of how it works.

You can of course download _oUF_Layout_ and try to customize it for your own needs if you think that this better suits the way you learn.

## Installation

_oUF_Layout_ is not meant for installation. You should rather recreate the layout yourself by following the commits. You have to install the dependencies separately as those are not embedded into the addon. Take a look at [oUF_Layout.toc](https://github.com/Rainrider/oUF_Layout/blob/master/oUF_Layout.toc) for a list of required and optional dependencies.

You should also install addons for capturing and displaying errors in-game. [!BugGrabber](http://www.wowinterface.com/downloads/info23141-BugGrabber.html) and [BugSack](http://www.wowinterface.com/downloads/info5995-BugSack.html) are a good choice.

If you however want to just install the layout and use it as is, you can download it [here](https://github.com/Rainrider/oUF_Layout/archive/master.zip). Rename the extracted folder to `oUF_Layout` and copy/move it to your `<WoW folder>\Interface\AddOns` folder.

If you are using _git_, you can issue the following commands:
  1. `cd <WoW folder>\Interface\AddOns`
  2. `git clone https://github.com/Rainrider/oUF_Layout.git`

## Debugging

[AdiDebug](https://github.com/Adirelle/AdiDebug) has been added as an optionial dependency to aid in debugging. The `Debug` function is added
to the addon's namespace and can be called like `ns.Debug('prefix', 'message')`, where 'prefix' is an optional string you could use for 
grouping messages, and 'message' is your debug output. It is a vararg function, so you can pass as many arguments to it as you wish. Objects 
and values passed to it will be coersed into their string representation.

Open AdiDebug by using the `/ad` or `/adidebug` slash commands and then select oUF_Layout from the dropdown menu to see your debug messages.

## Code Structure

The code structure has evolved during the development of _oUF_Layout_. The current state is as follows:

  - `assets` - contains fonts and textures
  - `elements` - contains code for consuming oUF elements
  - `elements\custom` - contains implementation of custom oUF elements
  - `units` - contains the style functions for the different units divided by style type
  - `fonts.xml` - a XML font template
  - `layout.lua` - uses `oUF:Factory` to spawn and style the frames for all units by calling their respective style functions
  - `settings.lua` - the configuration file
  - `utility.lua` - contains some utility functions and auxiliary stuff

## Visual Guide

Use this to compare your state to the one shown in the screenshots

| Commit link | Description | Screenshot |
| --- | --- | :---: |
| [0862c4](https://github.com/Rainrider/oUF_Layout/commit/0862c470863112e885f4aff45953d588b3d150ac) | player and target frames' backdrop | |
| [2b43c7](https://github.com/Rainrider/oUF_Layout/commit/2b43c733cf5338a8bb8296e7e4817aa1f29dbc4e) | health bars | |

## Getting Help

You can get help in the [oUF section of the WoWInterface forums](http://www.wowinterface.com/forums/forumdisplay.php?f=87), but please keep the following in mind:

  - put some effort in answering your question yourself before asking others for help, and demonstrate this effort when asking the question
  - be able to show all your code
  - be receptive for feedback and suggestions

