#!/bin/bash
clear
echo "|------------------|"
echo "|        1         |"
echo "|------------------|"

read numb
if [ $numb = "1" ]
then
	pkg install python
	pkg install python3
	pkg install python3-pip
	pip3 install requests
	pip3 install colorama
	cp ~/spymer/spammer.py /data/data/com.termux/files/usr/bin/spymer
	dos2unix /data/data/com.termux/files/usr/bin/spammer
	chmod 777 /data/data/com.termux/files/usr/bin/spammer
	spymer
else
	if [ $numb = "2" ]
	then

		if [ "$(whoami)" != 'root' ]; then
			echo "У вас нет прав. Запустите install.sh с root правами (sudo sh ~/spymer/install.sh)"
			exit
		else
			apt install python3 python3-pip
			pip3 install requests
			pip3 install colorama
			cp ~/spymer/spammer.py /usr/bin/spymer
			dos2unix /usr/bin/spymer
			chmod 777 /usr/bin/spymer
			spymer
		fi
	else
		echo "Некорректный ввод"
	fi
fi