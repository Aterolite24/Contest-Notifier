# How to build application for Linux System?

### Dependencies
```
sudo apt install python3-gi
```
```
sudo apt install pkg-config libcairo2-dev gcc python3-dev libgirepository1.0-dev
pip install PyGObject
```

###  Create a Desktop Entry File

A desktop entry file is a simple text file with a .desktop extension that contains metadata about your application. This file is used by desktop environments (like GNOME, KDE, etc.) to display information and launch applications.

Create a new file named myprogram.desktop with the following content:

```
[Desktop Entry]
Name=My Program
Comment=A demo program using Gtk and Python
Exec=/usr/bin/python3 /path/to/your/script.py
Icon=/path/to/your/icon.png
Terminal=false
Type=Application
Categories=Development;GTK;
```


### Set Execute Permissions
Make the myprogram.desktop file executable:
```
chmod +x myprogram.desktop
```


### Create an Icon

Create an icon file (icon.png) that you want to use for your application. This should be a square PNG file.


### Package Your Application

To simplify distribution, you can package your application into a distributable format. One common method is using pyinstaller to create a standalone executable.

Install pyinstaller if you haven't already:
```
pip install pyinstaller
```
Then create a standalone executable:
```
pyinstaller --onefile your_script.py
```
This will create a dist/ directory with an executable that users can run without needing to install Python or any dependencies.


### Distribute Your Application
Once you have the myprogram.desktop file and (if applicable) the packaged executable, you can distribute your application.
Place the myprogram.desktop file in ~/.local/share/applications/:

```
cp myprogram.desktop ~/.local/share/applications/
```

