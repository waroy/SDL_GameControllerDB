# SDL_GameControllerDB

A community sourced database of game controller mappings to be used with SDL2 Game Controller functionality.

# Usage
Download gamecontrollerdb.txt, place it in your app's directory and load it.

For example :
```
SDL_GameControllerAddMappingsFromFile("gamecontrollerdb.txt");
```

The database is compatible with SDL v2.0.10 and newer. Older SDL versions are no longer supported.

## Create New Mappings
A mapping looks like this :
```
030000004c050000c405000000010000,PS4 Controller,a:b1,b:b2,back:b8,dpdown:h0.4,dpleft:h0.8,dpright:h0.2,dpup:h0.1,guide:b12,leftshoulder:b4,leftstick:b10,lefttrigger:a3,leftx:a0,lefty:a1,rightshoulder:b5,rightstick:b11,righttrigger:a4,rightx:a2,righty:a5,start:b9,x:b0,y:b3,platform:Mac OS X,
```
It includes controller GUID (`030000004c050000c405000000010000`), a name (`PS4 Controller`), button / axis mappings (`leftshoulder:b4`) and a platform (`platform:Mac OS X`).

Please make sure to check that the name is a good description of the controller. If relevant, include the controller's name and model number.

## Mapping Tools
There are a few different tools that let you create mappings.

### [SDL2 Gamepad Tool](http://www.generalarcade.com/gamepadtool/)
Third party cross-platform tool with GUI (Windows, macOS and Linux). Likely the easiest tool to use.

#### Note: While convenient, this tool has fallen out of date as SDL has amended and added additional features for gamepad support: [#478](https://github.com/gabomdq/SDL_GameControllerDB/issues/476). As such, maps authored with this tool require greater scrutiny to ensure they will not break support for explicit mappings the SDL project provides. Maintainers of this repo are seeking an alternative (for example the tool immediately below) with up to date binaries provided to ease contribiution to and maitenance of this repo. If you use this database in production, please consider helping out!

### [SDL2 Gamepad Mapper](https://gitlab.com/ryochan7/sdl2-gamepad-mapper)

Open source replacement for older SDL2 Gamepad Tool.

### [SDL2 ControllerMap](https://www.libsdl.org/download-2.0.php)
The controllermap utility provided with SDL2 is the official tool to create these mappings, it runs on all the platforms SDL runs (Windows, Mac, Linux, iOS, Android, etc).

### [Steam](http://store.steampowered.com)
In Steam's Big Picture mode, configure your joystick. Then look in `[steam_installation_directory]/config/config.vdf` in your Steam installation directory for the `SDL_GamepadBind` entry. It is one of the last entries, it will look something like this:

```
"SDL_GamepadBind"		"030000004c050000c405000000010000,PS4 Controller,platform:Windows,a:b1,b:b2,back:b8,dpdown:h0.4,dpleft:h0.8,dpright:h0.2,dpup:h0.1,guide:b12,leftshoulder:b4,leftstick:b10,lefttrigger:a3,leftx:a0,lefty:a1,rightshoulder:b5,rightstick:b11,righttrigger:a4,rightx:a2,righty:a5,start:b9,x:b0,y:b3,"
```

### Additional Tools
[GNOME Games](https://wiki.gnome.org/Apps/Games) allows users to configure their own gamepads in GNU/Linux. The gamepad file the user generates is located at `~/.var/app/org.gnome.Games/config/libmanette/gamecontrollerdb` when installed from the flatpak. [AntiMicroX](https://github.com/AntiMicroX/antimicrox/) offers a GUI tool for configuring controller profiles in GNU/Linux and generating SDL2 controller profiles.


## Resources

* [SDL2](http://www.libsdl.org)
* [SDL_GameControllerAddMappingsFromFile](http://wiki.libsdl.org/SDL_GameControllerAddMappingsFromFile)
