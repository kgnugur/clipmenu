clipmenu is a simple clipboard manager using [dmenu][] (or [rofi][] with
`CM_LAUNCHER=rofi`) and [xsel][].


# Usage
Start `clipmenud`, then run `clipmenu` to select something to put on the
clipboard.

`clipmenu-url` Will work the same way expect it has a addition it will open the
selected line with default browser.
- If chosen line is not a link, search it with a search engine (default is
  duckduckgo).
- If chosen line is a link open it with browser

You can run the scripts standalone or you can just get the `clipmenu-url`.

## Example default setup
export BROWSER="firefox"
export SEARCHENGINE="google"

# Example dwm config
`
static const char *clipcmd[]  = { "clipmenu", "-fn", dmenufont, NULL };
static const char *urlcmd[]  = { "clipmenu-url", "-fn", dmenufont, NULL };
`
MODKEY is alt by default in dwm. Alt+Insert is the clipboard history menu. Alt+o opens clipmenu-url.

`
{ MODKEY,                       XK_Insert, spawn,          {.v = clipcmd } },
{ MODKEY,                       XK_o,      spawn,          {.v = urlcmd } },
`
