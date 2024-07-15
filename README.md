# nuebase v0.0.1-stable
- NueBase is a project manager for nue programs.
- Current Stable Version `0.0.1`. 

**Features:**
- You can create and run nue programs easily with the help of `.\nb.exe`.

*Note:*
- Put the `NueStuff` dir in your system programs dir, example = `C:\Program Files\NueStuff`

*Example Usage:*
  ```shell
  .\nb.exe
  ```
  *Output:*
  ```shell
  Usage:
  nb new <projectname>                      :: Create a new project with the given name.
  nb run                                    :: Run the default main file specified in nue-conf.json.
  nb run -s <scriptname>                    :: Run a specific script specified in nue-conf.json.
  nb del <projectname>                      :: Delete the project directory.
  nb conf init <projectname>                :: Initialize a new nue-conf.json file for the project.
  nb conf <name> <value>                    :: Update nue-conf.json with the specified name and value.
  nb conf -s <scriptname> <scriptlocation>  :: Add a script to nue-conf.json.
  nb conf -s -cc                            :: Check if all script files are present in their registered directories.
  ```
*Complete GoThrough:*
```shell
PS E:\fri3nds\y-category-Projects\Nue3\Release> .\nb.exe new supercoolproject    
Configuration file 'supercoolproject\nue-conf.json' initialized successfully.
Project 'supercoolproject' created successfully.
PS E:\fri3nds\y-category-Projects\Nue3\Release> cd supercoolproject


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         7/15/2024  11:58 AM                nuepkgs
-a----         7/15/2024  11:58 AM             60 main.nue
-a----         7/15/2024  11:58 AM            121 nue-conf.json

PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> echo "console.Println(console.Println("Welcome from @Main2.nue"))" >> main2.nue
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe conf deafult-main main2.nue        
Error: Unknown configuration parameter 'deafult-main'
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe conf default-main main2.nue
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe run
> nue main2.nue
Welcome from @Main2.nue
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe conf default-main main.nue
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe run
hello worlds!
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe conf -s newscript main2.nue
Script 'newscript' added successfully: 'main2.nue'
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe run -s newscript
> nue main2.nue
Welcome from @Main2.nue
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe run -s newscript
> nue main2.nue
Welcome from @Main2.nue
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe run -s -cc #oops there is an error or a conf mistake, i think?    
Error: Script '-cc' not found in configuration.
PS E:\fri3nds\y-category-Projects\Nue3\Release\supercoolproject> ..\nb.exe del supercoolproject
Project 'supercoolproject' deleted successfully.
```
