trashcaron
==========
<br>
Trashcaron (acronym for 'trash care python') allows you to delete files/folders to a trashbin. Moreover you can
purge trashed files after a specified time for all trashbins. You can also list the size of each existing trashbin
on the system.

<br>
#### Command usage
```
usage: trashcaron.py [-h] [-d [DELETE [DELETE ...]]] [-l] [-pt PURGETIME] [-v]
                     [-vv]

With trashcaron you can delete files to a trashbin and delete old files for
all trashbins automatically after a specified amount of time.

optional arguments:
  -h, --help            show this help message and exit
  -d [DELETE [DELETE ...]], --delete [DELETE [DELETE ...]]
                        File/Dir to be deleted
  -l, --listtrashsizes  du for all trashbins
  -pt PURGETIME, --purgetime PURGETIME
                        Purge time for all trashbins in currently mounted
                        filesystems. Time in minutes. Just write the number of
                        minutes. Don't append a letter to the number.
  -v, --info            Log level: info
  -vv, --debug          Log level: debug
```
<br>

#### Tips
- I'd recommend to create a bashfile in cron.daily to purge files from the trashbin automatically. To purge files
older than 10 days put e.g. this file to /etc/cron.daily/:
```
`/path/to/trashcaron.py -pt 10`

- I use these bash aliases for trashcaron.py: 
```
alias rm="/path/to/trashcaron.py -v -d"
alias rmlist="sudo /path/to/trashcaron.py -l"
alias srm="sudo /path/to/trashcaron.py -v -d"
alias rmpurge="sudo /path/to/trashcaron.py -v -pt"
```
