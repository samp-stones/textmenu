# textmenu

[![sampctl](https://img.shields.io/badge/sampctl-textmenu-2f2f2f.svg?style=for-the-badge)](https://github.com/samp-stones/textmenu)

<!--
Short description of your library, why it's useful, some examples, pictures or
videos. Link to your forum release thread too.

Remember: You can use "forumfmt" to convert this readme to forum BBCode!

What the sections below should be used for:

`## Installation`: Leave this section un-edited unless you have some specific
additional installation procedure.

`## Testing`: Whether your library is tested with a simple `main()` and `print`,
unit-tested, or demonstrated via prompting the player to connect, you should
include some basic information for users to try out your code in some way.

And finally, maintaining your version number`:

* Follow [Semantic Versioning](https://semver.org/)
* When you release a new version, update `VERSION` and `git tag` it
* Versioning is important for sampctl to use the version control features

Happy Pawning!
-->

## Installation

Simply install to your project:

```bash
sampctl package install samp-stones/textmenu
```

Include in your code and begin using the library:

```pawn
#include <textmenu>
```

## Usage

<!--
Write your code documentation or examples here. If your library is documented in
the source code, direct users there. If not, list your API and describe it well
in this section. If your library is passive and has no API, simply omit this
section.
-->

## Testing

<!--
Depending on whether your package is tested via in-game "demo tests" or
y_testing unit-tests, you should indicate to readers what to expect below here.
-->

To test, simply run the package:

```bash
sampctl package run
```

##  Functions

```pawn
TextMenuShowForPlayer(playerid,menuid,header[],content[],items=0)
TextMenuHideForPlayer(playerid) 
```

## Callbacks
```pawn
forward OnTextMenuResponse(playerid,menuid,listitem); 
```

## Example

```pawn
CMD:test(playerid)
{
    new Test[600],bool:necessary = true;
    if(necessary)
    {
          strcat(Test,"~y~1-~w~ Message 1~n~");
          strcat(Test,"~y~2-~w~ Message 2~n~");
          strcat(Test,"~y~3-~w~ Message 3~n~");
          strcat(Test,"~y~4-~w~ Message 4~n~");
          strcat(Test,"~y~5-~w~ Message 5~n~");
          strcat(Test,"~y~6-~w~ Message 6");
          necessary = false;
     }
     TextMenuShowForPlayer(playerid,0,"Items",Test,6);
     return 1;
}

public OnTextMenuResponse(playerid,menuid,listitem)
{
     if(menuid == 0)
     {
          switch(listitem)
          {
                case 1:
                {
                      //Your code
                }
                case 2:
                {
                      //Your stuff
                }
                case 3:
                {
                      //Your code
                }
                case 4:
                {
                      //Your code
                }
                case 5:
                {
                      //Your code
                }
                case 6:
                {
                      //Your code
                }    
          }       
     }
     return 1;    
} 
```
