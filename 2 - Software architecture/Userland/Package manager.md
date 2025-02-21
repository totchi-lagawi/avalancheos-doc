# Package manager
Every software is a package : Firefox, Thunderbird, XFCE...

Sample package configuration :
```toml
[Description]
Name=Firefox
Description=A browser
Id=org.mozilla.firefox
Version=135.28.3
Languages = ["en", "fr", "es", "(...)"]

[Dependencies]
libc = 2.3

[Entry Points]
main = "/firefox"
private_window = {
    command = "/firefox --private-window",
    comment = {
        "en" = "Start Firefox in a private window",
        "fr" = "Démarrer Firefox dans une fenêtre privée"
    }
}

[Install]
executables = ["/firefox", "/firefox-helper"]
```

```toml
# Everything is denied by default

# Hard permissions are required by the application
[Hard Permissions]
graphical = true
network = ["tcp"]
# Environment variables allow to not depend on the hierarchy of the VFS
# Problem : what if the download path isn't $HOME.DOWNLOADS.PATH
files = ["$HOME.DOWNLOADS.PATH"]

# Soft permissions aren't required, but are for some functionnalies
[Soft Permissions]
camera = true
microphone = true
# If the requested path is in $HOME.PATH, then the permission for $HOME.PATH is asked. Otherwise, the permission for full filesystem access is given
files = ["$HOME.PATH", "/"]
```

```toml
[Build Dependencies]
com.kitware.cmake = 3.31.4
# Which depends on rustc, etc.
org.rust-lang.cargo = 1.84.0

[Libraries]
libc = {
    version = 2.3,
    # NOTE
    # Until the linking mode of the library can be controlled by the build system, this is ONLY an indication
    mode = "dynamic"
}

[Build]
actions = [
    "cmake --prepare-files",
    "cmake build"
]

[Package]
files = {
    "/" = "/build",
    # Would that be automatically added? - Yes
    "/package.toml" = "/package.toml",
    "/permissions.toml" = "/permissions.toml"
}
```