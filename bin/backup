#!/bin/sh
#-----------------------------------------------------------------------------
#
#	<backup.sh> - A Pure Data backup utility
#
#	Automatically generated from <pdstart>
#
#	Usage: from <bin> directory holding <>, run 
#
#	$ sh backup.sh
#
#-----------------------------------------------------------------------------

#	Directory holding backups
BAKDIR=bak

#	<bin> directory holding all you need to backup
BINDIR=bin

#	Help
BAKHELP="
This backup utility is created by <pdstart> to ease the creation of backups
as your project gets bigger and bigger.	This backup utility resides 
in the root folder (aka. <name>) with links created on each working <bin>. 

Usage:
	$ cd bin
	$ sh backup

All your backups are created in the <bak> directory	with increasing indeces.

Enjoy and if you have any issues, please contact me at <fdch.github.io>
"

if [[ $1 ]]; then
	echo "$BAKHELP"
	exit
fi

#	Find next backup item nubmer
i=1

if [[ -d ../$BAKDIR/${BINDIR}_1 ]] ; then
	for dirs in ../$BAKDIR/* ; do 
		((i++))
	done
fi

BAKFILE=${BINDIR}_${i}

echo "Backing up $BINDIR into $BAKDIR/$BAKFILE ..."

rsync -aP --exclude=backup ../$BINDIR/* ../$BAKDIR/$BAKFILE

exit
