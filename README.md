# Run As Limited Library

# Add run as limited to your application!
Example of usage: https://github.com/KayleMine/RunAsLimited2

## init
```c#
RunAsLibrary.Api Api = new RunAsLibrary.Api();
```

## Create(string NameLog, string Pass)
```c#
Api.Create("name", "1")
```
```
Will create user with login 'name' and password '1'
```

## Remove(string NameLog)
```c#
Api.Remove("name")
```
```
Will delete user with login 'name'
```

## GetInfo(string NameLog)
```c#
Api.GetInfo("name")
```
```
Will open cmd window with info about user with name 'name'.
But if called like: GetInfo("") then just show all existing users on pc.
```

## Get_FolderPath() && Get_Exe()
```c#
    private void Select_App_Click(object sender, EventArgs e)
    {
    path = Api.Get_FolderPath();
    path_exe = Api.Get_Exe();
    ...
    }
```
```
1st get path to folder, 2nd get exe name in that folder.
```

## run_target(string path, string path_exe, string NameLog, string Pass, string args)
```c#
Api.run_target("C:\\appfolder", "app.exe", "name", "password", "-console");
```
```
Will run application (exe) from folder you select, from user you created, args can be "" if not need.
```

## SaveCfg(params KeyValuePair<string, string>[] keyValuePairs)
```c#
    Api.SaveCfg(
    new KeyValuePair<string, string>("path", path),
    new KeyValuePair<string, string>("path_exe", path_exe)
    );
```
```

new KeyValuePair<string, string>("key", variable)

Save your "key", var to config.json near application.
```

## ReadCfg(string key)
```c#
path = Api.ReadCfg("path");
```
```
Get your config data by key.
```
