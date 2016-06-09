#Agrep
###Asynchronous grep plugin for Vim

**_\*\*This plugin is under development\*\*_**

__Features:__

- Run grep at the background and get the live stream of results into Vim.
  The results will be displayed in a special window as soon as they are
  found, you can keep working or start exploring the list immediately.
- Jump to the exact location of a match (line and column. Also for multiple
  matches in a line).
- Highlighting the matching text.

![Agrep](http://i.imgur.com/epffEDH.gif)

__Usage:__  
Agrep takes the same command line arguments as the shell's grep, for example:

:Agrep -r 'foo.*bar' ~/my_project

It uses -nH flags by default so you don't need to specify them explicitly.

The results are displayed in a special window which is not the quickfix
window by default (at least for now). You can change this and load the
results directly to the quickfix list but it is slower for very long lists.
You can load the results to the quickfix list any time by running :Aquickfix.
It is useful when you edit the files while navigating the list.  
The following commands can be used to navigate the search results (non
quickfix mode):

- AA [nr]
- Anext
- Aprev
- Aopen
- Aclose

These commands are similar to the corresponding quickfix commands (cc, cn,
cp). Hitting Enter or double-clicking the mouse on a match in the Agrep
window will take you to the match location as well.
Use :Astop to kill the search and its grep process.

__Options:__
 
    agrep_default_flags : default '-I'
    agrep_win_height    : default 15
    agrep_use_qf        : default 0 (change it to 1 if you want Agrep to add the results directly to the quickfix list)

__TODO:__

- Handle tab switching while searching
- Update navigation commands (if quickfix will not be default eventually)
- Add :Agrepfilter command
