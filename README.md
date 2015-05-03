btcat is a small program written in Python. The latest version is available to download. It works in linux, and should work in other platforms without changes. I would appreciate reports about successful runs in platforms other than linux. It's released under a GPL licence, which means that it's free software. Please read the documentation below for installation notes and usage.

NAME

       btcat - download a torrent file from the network and output its contents to the standard output.

SYNOPSIS

       btcat is a command line tool that downloads a file using the bittorrent protocol and outputs its contents
       to the standard output. btcat streams the data sequentially, which allows processing the file in a
       pipeline before the whole transfer has been completed. It is possible, for instance, to reproduce a media
       file while it's still downloading.

SYNOPSIS

       btcat TORRENTFILE|TORRENTURL [FILEID]

DESCRIPTION

       if no FILEID is specified, a list of file names and file ids will be provided for torrents containing more
       than one file. If FILEID is specified, the program will initiate the download of the file and the contents
       will be dumped to the standard output.

EXAMPLES

              display a list of files and file ids on the torrent

       btcat 'http://www.clearbits.net/get/53-star-wreck---in-the-pirkinning.torrent'

              download the contents of the torrent flow and save it into a file

       btcat 'http://www.clearbits.net/get/53-star-wreck---in-the-pirkinning.torrent' 0 > download.avi

              reproduce a media file on the fly (audio or video)

       btcat 'http://www.clearbits.net/get/53-star-wreck---in-the-pirkinning.torrent' 0 | mplayer -

AUTHOR

       Written by Jordi Colomer. May 2011. jordikolomer@gmail.com

REPORTING BUGS
       Report ls bugs to jordikolomer@gmail.com

       License GPLv3+: GNU GPL version 3 or later
       .
       This is free software: you are free to change and redistribute it.
       There is NO WARRANTY, to the extent permitted by law.

INSTALLATION

       (in debian, ubuntu and derivates)
       sudo apt-get install python-libtorrent mplayer
       sudo wget http://jordic.com/btcat/btcat -O /usr/local/bin/btcat
       sudo chmod +x /usr/local/bin/btcat

