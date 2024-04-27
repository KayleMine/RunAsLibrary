# Run As Limited Library
 

### Add Run-as to your software!
***
> [!TIP]
> For what? 
> For protection, it allow to bypass World of Warcraft Warden scans, same for Path Of Exile AC, and many others AC that not use driver's.
> 
> Now after we launched game, from limited user, it can't check any-administrator related stuff, that we run, for example in poe it would be POEHud, in WoW, any kind rotation\bot\fishbot and etc.
***
#### Example of usage:
[RunAsLimited 2](https://github.com/KayleMine/RunAsLimited2/tree/main)



#### init lib
```c#
RunAsLibrary.Api Api = new RunAsLibrary.Api();
```

#### Create user
```c
  Api.Create("name", "1") //Will create user with login 'name' and password '1'
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `text` | `string` | UserName |
| `text` | `string` | Password |


#### Remove user
```c
  Api.Remove("name") // Will remove user with login 'name'.
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `text` | `string` | UserName |
 
#### Get user info
```c
  Api.GetInfo("name") // Will get info about user with login 'name'.
  Api.GetInfo("")     // Will append list of users on pc.
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `text` | `string` | UserName or ""|


### Get folder path and exe name
```c#
    private void Select_App_Click(object sender, EventArgs e) // an example
    {
    path = Api.Get_FolderPath();
    path_exe = Api.Get_Exe();
    ...
    }
```
```
1st call will let select folder, 2nd get exe name in that folder.
```

#### Run app
```c
Api.run_target("C:\\appfolder", "app.exe", "name", "password", "-console"); // will start app.exe under user name with -console
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `text` | `string` | Path to folder |
| `text` | `string` | Exe name |
| `text` | `string` | UserName |
| `text` | `string` | Password |
| `text` | `string` | Startup args |

#### Save config
```c#
Api.SaveCfg(                                              // An example
    new KeyValuePair<string, string>("path", path),
    new KeyValuePair<string, string>("path_exe", path_exe)
);
```
| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `string` | `string` | Key |
| `string` | `string` | Value |



#### Read config
```c#
Api.ReadCfg("path"); // Get your config data by key.
```
| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `string` | `string` | Key |


