```
底下指令有何差異?
ls
ls -l
ls -Al
ls -al
```

# ls指令測試
#### ls
```
lab@29d4cf5af0ab:~$ ls
base64.txt  flag  hex.txt
```
```
cat flag
```
```
BreakALLCTF{Sobkjgd14VuIFBUtgVts}
```
#### ls -l
```
lab@29d4cf5af0ab:~$ ls -l
total 12
-rw-rw-r-- 1 root root 46 Nov 20  2017 base64.txt
-rw-rw-r-- 1 root root 35 Nov 15  2017 flag
-rw-rw-r-- 1 root root 68 Nov 20  2017 hex.txt
lab@29d4cf5af0ab:~$
```
#### ls -Al
```
lab@29d4cf5af0ab:~$ ls -Al
total 28
-rw-r--r-- 1 lab  lab   220 Apr 26 14:48 .bash_logout
-rw-r--r-- 1 root root 3771 Apr 26 14:48 .bashrc
-rw-rw-r-- 1 root root   34 Nov 19  2017 .hidden
-rw-r--r-- 1 lab  lab   655 Apr 26 14:48 .profile
-rw-rw-r-- 1 root root   46 Nov 20  2017 base64.txt
-rw-rw-r-- 1 root root   35 Nov 15  2017 flag
-rw-rw-r-- 1 root root   68 Nov 20  2017 hex.txt
```
#### ls -al
```
lab@29d4cf5af0ab:~$ ls -al
total 36
drwxr-xr-x 1 root root 4096 Apr 26 14:48 .
drwxr-xr-x 1 root root 4096 Apr 26 14:48 ..
-rw-r--r-- 1 lab  lab   220 Apr 26 14:48 .bash_logout
-rw-r--r-- 1 root root 3771 Apr 26 14:48 .bashrc
-rw-rw-r-- 1 root root   34 Nov 19  2017 .hidden
-rw-r--r-- 1 lab  lab   655 Apr 26 14:48 .profile
-rw-rw-r-- 1 root root   46 Nov 20  2017 base64.txt
-rw-rw-r-- 1 root root   35 Nov 15  2017 flag
-rw-rw-r-- 1 root root   68 Nov 20  2017 hex.txt
```
#### 指令與指令參數
```
command(指令) line 
options 參數
```
## 指令參數的學習
```
ls -h
ls --h
ls -help
ls --help
```
```
到google 搜尋linux ls
```
```
https://blog.gtwang.org/linux/linux-ls-command-tutorial/
```
# ls 詳細參數
```
lab@29d4cf5af0ab:~$ ls --help
Usage: ls [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).
Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

Mandatory arguments to long options are mandatory for short options too.
  -a, --all                  do not ignore entries starting with .
  -A, --almost-all           do not list implied . and ..
      --author               with -l, print the author of each file
  -b, --escape               print C-style escapes for nongraphic characters
      --block-size=SIZE      scale sizes by SIZE before printing them; e.g.,
                               '--block-size=M' prints sizes in units of
                               1,048,576 bytes; see SIZE format below
  -B, --ignore-backups       do not list implied entries ending with ~
  -c                         with -lt: sort by, and show, ctime (time of last
                               modification of file status information);
                               with -l: show ctime and sort by name;
                               otherwise: sort by ctime, newest first
  -C                         list entries by columns
      --color[=WHEN]         colorize the output; WHEN can be 'always' (default
                               if omitted), 'auto', or 'never'; more info below
  -d, --directory            list directories themselves, not their contents
  -D, --dired                generate output designed for Emacs' dired mode
  -f                         do not sort, enable -aU, disable -ls --color
  -F, --classify             append indicator (one of */=>@|) to entries
      --file-type            likewise, except do not append '*'
      --format=WORD          across -x, commas -m, horizontal -x, long -l,
                               single-column -1, verbose -l, vertical -C
      --full-time            like -l --time-style=full-iso
  -g                         like -l, but do not list owner
      --group-directories-first
                             group directories before files;
                               can be augmented with a --sort option, but any
                               use of --sort=none (-U) disables grouping
  -G, --no-group             in a long listing, don't print group names
  -h, --human-readable       with -l and/or -s, print human readable sizes
                               (e.g., 1K 234M 2G)
      --si                   likewise, but use powers of 1000 not 1024
  -H, --dereference-command-line
                             follow symbolic links listed on the command line
      --dereference-command-line-symlink-to-dir
                             follow each command line symbolic link
                               that points to a directory
      --hide=PATTERN         do not list implied entries matching shell PATTERN
                               (overridden by -a or -A)
      --indicator-style=WORD  append indicator with style WORD to entry names:
                               none (default), slash (-p),
                               file-type (--file-type), classify (-F)
  -i, --inode                print the index number of each file
  -I, --ignore=PATTERN       do not list implied entries matching shell PATTERN
  -k, --kibibytes            default to 1024-byte blocks for disk usage
  -l                         use a long listing format
  -L, --dereference          when showing file information for a symbolic
                               link, show information for the file the link
                               references rather than for the link itself
  -m                         fill width with a comma separated list of entries
  -n, --numeric-uid-gid      like -l, but list numeric user and group IDs
  -N, --literal              print raw entry names (don't treat e.g. control
                               characters specially)
  -o                         like -l, but do not list group information
  -p, --indicator-style=slash
                             append / indicator to directories
  -q, --hide-control-chars   print ? instead of nongraphic characters
      --show-control-chars   show nongraphic characters as-is (the default,
                               unless program is 'ls' and output is a terminal)
  -Q, --quote-name           enclose entry names in double quotes
      --quoting-style=WORD   use quoting style WORD for entry names:
                               literal, locale, shell, shell-always,
                               shell-escape, shell-escape-always, c, escape
  -r, --reverse              reverse order while sorting
  -R, --recursive            list subdirectories recursively
  -s, --size                 print the allocated size of each file, in blocks
  -S                         sort by file size, largest first
      --sort=WORD            sort by WORD instead of name: none (-U), size (-S),
                               time (-t), version (-v), extension (-X)
      --time=WORD            with -l, show time as WORD instead of default
                               modification time: atime or access or use (-u);
                               ctime or status (-c); also use specified time
                               as sort key if --sort=time (newest first)
      --time-style=STYLE     with -l, show times using style STYLE:
                               full-iso, long-iso, iso, locale, or +FORMAT;
                               FORMAT is interpreted like in 'date'; if FORMAT
                               is FORMAT1<newline>FORMAT2, then FORMAT1 applies
                               to non-recent files and FORMAT2 to recent files;
                               if STYLE is prefixed with 'posix-', STYLE
                               takes effect only outside the POSIX locale
  -t                         sort by modification time, newest first
  -T, --tabsize=COLS         assume tab stops at each COLS instead of 8
  -u                         with -lt: sort by, and show, access time;
                               with -l: show access time and sort by name;
                               otherwise: sort by access time, newest first
  -U                         do not sort; list entries in directory order
  -v                         natural sort of (version) numbers within text
  -w, --width=COLS           set output width to COLS.  0 means no limit
  -x                         list entries by lines instead of by columns
  -X                         sort alphabetically by entry extension
  -Z, --context              print any security context of each file
  -1                         list one file per line.  Avoid '\n' with -q or -b
      --help     display this help and exit
      --version  output version information and exit

The SIZE argument is an integer and optional unit (example: 10K is 10*1024).
Units are K,M,G,T,P,E,Z,Y (powers of 1024) or KB,MB,... (powers of 1000).

Using color to distinguish file types is disabled both by default and
with --color=never.  With --color=auto, ls emits color codes only when
standard output is connected to a terminal.  The LS_COLORS environment
variable can change the settings.  Use the dircolors command to set it.

Exit status:
 0  if OK,
 1  if minor problems (e.g., cannot access subdirectory),
 2  if serious trouble (e.g., cannot access command-line argument).

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
Report ls translation bugs to <http://translationproject.org/team/>
Full documentation at: <http://www.gnu.org/software/coreutils/ls>
or available locally via: info '(coreutils) ls invocation'
```
# ls詳細參數翻譯
```
lab@29d4cf5af0ab:~$ 指令 --幫忙
運用: 指令 [選項]... [檔案]...
列出有關檔案的信息(當前目錄默認)
如果沒有，則按字母順序對條目排序 -cftuvSUX也不 --指定了排序。

強制選擇長選項，短選項也是強制選擇。
 -a, --所有                  不要忽略開頭的條目。
  -A, --幾乎所有              不列出隱含 . 和 ..
      --作家                 關於 -l, 打印每個作者的文件
  -b, --逃逸                 打印 C-非圖形字符的樣式轉義
      --分段-大小=SIZE        打印之前按SIZE縮放尺寸; e.g.,
                             '--分段-大小=M' 打印尺寸，單位為1,048,576 bytes; 請參閱下面的尺寸格式
  -B, --忽略-備份             不列出結尾隱含項 ~
  -c                         關於 -lt: 排序並顯示, 時間 (最後修改檔案狀態信息的時間);
                             關於 -l: 顯示時間並按名稱排序;
                             除此以外: 按時間排序，最新的優先。
  -C                         按列列出條目
      --顏色[=何時]           著色輸出; 何時可以“總是” (如果省略則默認), '自動', 或 '從不'; 下面更多信息
  -d, --目錄                 列出目錄本身, 不是他們的內容。
  -D, --目錄編輯器            生成為純文字編輯器設計的輸出' 目錄編輯器模式
  -f                         不排序, 使能... -aU, 禁用 -指令 --顏色
  -F, --分類                 追加指標 (之一 */=>@|) 進入
      --檔案-類型            同樣, 除了不附加 '*'
      --格式=WORD            跨越 -x, 逗號 -m, 水平的 -x, 長 -l,
                            單欄 -1, 冗長的 -l, 垂直 -C
      --全職                 像--時間風格=全iso檔
      -g                     像 -l, 但不列出所有者
      --組目錄優先
                             檔案前組目錄;
                             可以使用--排序選項, 但是任何
                              用於 --sort=none (-U) disables grouping
  -G, --no-group             in a long listing, don't print group names
  -h, --human-readable       with -l and/or -s, print human readable sizes
                               (e.g., 1K 234M 2G)
      --si                   likewise, but use powers of 1000 not 1024
  -H, --dereference-command-line
                             follow symbolic links listed on the command line
      --dereference-command-line-symlink-to-dir
                             follow each command line symbolic link
                               that points to a directory
      --hide=PATTERN         do not list implied entries matching shell PATTERN
                               (overridden by -a or -A)
      --indicator-style=WORD  append indicator with style WORD to entry names:
                               none (default), slash (-p),
                               file-type (--file-type), classify (-F)
  -i, --inode                print the index number of each file
  -I, --ignore=PATTERN       do not list implied entries matching shell PATTERN
  -k, --kibibytes            default to 1024-byte blocks for disk usage
  -l                         use a long listing format
  -L, --dereference          when showing file information for a symbolic
                               link, show information for the file the link
                               references rather than for the link itself
  -m                         fill width with a comma separated list of entries
  -n, --numeric-uid-gid      like -l, but list numeric user and group IDs
  -N, --literal              print raw entry names (don't treat e.g. control
                               characters specially)
  -o                         like -l, but do not list group information
  -p, --indicator-style=slash
                             append / indicator to directories
  -q, --hide-control-chars   print ? instead of nongraphic characters
      --show-control-chars   show nongraphic characters as-is (the default,
                               unless program is 'ls' and output is a terminal)
  -Q, --quote-name           enclose entry names in double quotes
      --quoting-style=WORD   use quoting style WORD for entry names:
                               literal, locale, shell, shell-always,
                               shell-escape, shell-escape-always, c, escape
  -r, --reverse              reverse order while sorting
  -R, --recursive            list subdirectories recursively
  -s, --size                 print the allocated size of each file, in blocks
  -S                         sort by file size, largest first
      --sort=WORD            sort by WORD instead of name: none (-U), size (-S),
                               time (-t), version (-v), extension (-X)
      --time=WORD            with -l, show time as WORD instead of default
                               modification time: atime or access or use (-u);
                               ctime or status (-c); also use specified time
                               as sort key if --sort=time (newest first)
      --time-style=STYLE     with -l, show times using style STYLE:
                               full-iso, long-iso, iso, locale, or +FORMAT;
                               FORMAT is interpreted like in 'date'; if FORMAT
                               is FORMAT1<newline>FORMAT2, then FORMAT1 applies
                               to non-recent files and FORMAT2 to recent files;
                               if STYLE is prefixed with 'posix-', STYLE
                               takes effect only outside the POSIX locale
  -t                         sort by modification time, newest first
  -T, --tabsize=COLS         assume tab stops at each COLS instead of 8
  -u                         with -lt: sort by, and show, access time;
                               with -l: show access time and sort by name;
                               otherwise: sort by access time, newest first
  -U                         do not sort; list entries in directory order
  -v                         natural sort of (version) numbers within text
  -w, --width=COLS           set output width to COLS.  0 means no limit
  -x                         list entries by lines instead of by columns
  -X                         sort alphabetically by entry extension
  -Z, --context              print any security context of each file
  -1                         list one file per line.  Avoid '\n' with -q or -b
      --help     display this help and exit
      --version  output version information and exit

The SIZE argument is an integer and optional unit (example: 10K is 10*1024).
Units are K,M,G,T,P,E,Z,Y (powers of 1024) or KB,MB,... (powers of 1000).

Using color to distinguish file types is disabled both by default and
with --color=never.  With --color=auto, ls emits color codes only when
standard output is connected to a terminal.  The LS_COLORS environment
variable can change the settings.  Use the dircolors command to set it.

Exit status:
 0  if OK,
 1  if minor problems (e.g., cannot access subdirectory),
 2  if serious trouble (e.g., cannot access command-line argument).

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
Report ls translation bugs to <http://translationproject.org/team/>
Full documentation at: <http://www.gnu.org/software/coreutils/ls>
or available locally via: info '(coreutils) ls invocation'
```








