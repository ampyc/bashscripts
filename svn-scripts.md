# Remove already deleted files from SVN
from http://stackoverflow.com/questions/9600382/svn-command-to-delete-all-locally-missing-files

    svn st | grep ! | cut -d! -f2| sed 's/^ *//' | sed 's/^/"/g' | sed 's/$/"/g' | xargs svn rm
    
Explanation of all piped commands:
* Svn status
* Filter only on missing files (!)
* Cut out exclamation point
* Filter out trailing whitespaces
* Add leading quote
* Add trailing quote
* Svn remove each file

#Fix directory conflict
from http://stackoverflow.com/questions/3826663/fixing-a-directory-conflict-in-subversion

    svn resolve --accept=working /home/bob/dev/store/client
