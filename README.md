MenuV | Standalone Menu for FiveM | NUI Menu
N|CoreV

Issues License Forks Stars Discord

MenuV is a library written for FiveM and only uses NUI functionalities. This library allows you to create menus in FiveM. This project is open-source and you must respect the license and the hard work.

Features
Support for simple buttons, sliders, checkboxes, lists and confirms
Support for emojis on items
Support for custom colors (RGB)
Support for all screen resolutions.
Item descriptions
Rebindable keys
Event-based callbacks
Uses 2 msec while menu open and idle.
Documentation on menuv.fivem.io/api/
Themes: default or native
Compile files
MenuV uses VueJS and TypeScript with NodeJS. If you want to use the master files, you need to build the hole project by doing:

npm install
After you have downloaded/loaded all dependencies, you can build MenuV files by executing the following command:

npm run build
After the command is executed you will see a build folder containing all the resource files. Copy those files to a resource folder called menuv or create a symbolic link like that:

Windows
mklink /J "repositoryPath\build" "fxResourcesPath\menuv"
Linux
ln -s "repositoryPath\build" "fxResourcesPath\menuv"
You can also check this tutorial on how to make a link: https://www.howtogeek.com/howto/16226/complete-guide-to-symbolic-links-symlinks-on-windows-or-linux/

When your downloading a release, you don't have to follow this step, because all release version are build version.

How to use?
⚠️ example.lua can't be added in the menuv fxmanifest, you must make an seperate resource like: menuv_example

Add start menuv to your server.cfg before the resources that's uses menuv
To use MenuV you must add @menuv/menuv.lua in your fxmanifest.lua file.
client_scripts {
    '@menuv/menuv.lua',
    'example.lua'
}
Create a menu
Create a menu by calling the MenuV:CreateMenu function.

MenuV:CreateMenu(title: string, subtitle: string, position: string, red: number, green: number, blue: number, texture: string, disctionary: string, namespace: string, theme: string)
Example:

local menu = MenuV:CreateMenu('MenuV', 'Welcome to MenuV', 'topleft', 255, 0, 0, 'size-125', 'default', 'menuv', 'example_namespace', 'native')
Create menu items
Create a item by calling AddButton, AddConfirm, AddRange, AddCheckbox or AddSlider in the created menu

/** CREATE A BUTTON */
menu:AddButton({ icon: string, label: string, description: string, value: any, disabled: boolean });

/** CREATE A CONFIRM */
menu:AddConfirm({ icon: string, label: string, description: string, value: boolean, disabled: boolean });

/** CREATE A RANGE */
menu:AddRange({ icon: string, label: string, description: string, value: number, min: number, max: number, disabled: boolean });

/** CREATE A CHECKBOX */
menu:AddCheckbox({ icon: string, label: string, description: string, value: boolean, disabled: boolean });

/** CREATE A SLIDER */
menu:AddSlider({ icon: string, label: string, description: string, value: number, values: [] { label: string, value: any, description: string }, disabled: boolean });
To see example in practice, see example.lua

Events
In MenuV you can register event-based callbacks on menu and/or items.

/** REGISTER A EVENT ON MENU */
menu:On(event: string, callback: function);

/** REGISTER A EVENT ON ANY ITEM */
item:On(event: string, callback: function);
Documentation
Read MenuV documentation

License
Project is written by ThymonA and published under GNU General Public License v3.0 Read License

Screenshot
How is this menu made? see example.lua

Default	Native
MenuV Default	MenuV Native
Default Theme	Native Theme
