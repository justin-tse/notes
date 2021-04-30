## Vscode error
1. LiveServer error
```
"Open a folder or workspace... (File -> Open Folder)" when "> Live Server: Open with Live Server" without a folder being open #248
```
* Soution:
>
[Source](https://github.com/ritwickdey/vscode-live-server/issues/33)
@cohn17 I had some issues too. What I did was:

1. Create a folder under the root of the site, called .vscode
2. Add a file there, called settings.json
3. Edit the file and add the following:
``` {
    "liveServer.settings.root": "/dist"
}
```
(dist being the root folder I want the liveserver to know about)

Then I actually had to edit the global settings.json:

1. CTRL+SHIFT+P and type "Preferences".
2. Search for "liveserver" and click "Edit in settings.json"

![img](https://user-images.githubusercontent.com/1279436/55608716-4f098d80-577f-11e9-8dc5-6aaff35ba7b2.png)

I then added the same code inside my global settings.json:
![image](https://user-images.githubusercontent.com/1279436/55608761-6cd6f280-577f-11e9-8424-f50406c189b9.png)

Then launched liveserver, killed it, removed the setting in the global settings.json and then relaunched the server.
From now on, liveserver seems to follow whatever is written in the /.vscode/settings.json - file. Perhaps a bug in vscode?

And then the second problem will arise:
```Server is started at 5500 but failed to open in Browser Preview. Got Browser Preview extension installed```

Just
>[source](https://github.com/ritwickdey/vscode-live-server/issues/579)
I changed the value of the "liveServer.settings.useBrowserPreview" to false 


