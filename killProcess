#!/bin/bash

# @author: ajfernandez
# @date: 04-12-18
#
# killProcess -> Look for all process for a given username and kill them.

printf "\nEnter a username: "

userName=''
pid=0
nameFind=''

read a

printf "\nProcess of %s", $userName

ps -u $userName


printf "\nEnter the PID of the process to kill \
(Type 0 to find the PID according to a name): "

read pid

if [ $pid -eq 0 ]; then
	printf "\nEnter the name of process to find his PID: "
	read nameFind
	pid=$(pidof -s -x fetch-data $nameFind)
	printf "\nThe PID of %s is: %d\n", $nameFind $pid
fi

if [ $pid -ne 0 ]; then
	if [[ $(kill -9 $pid) -ne 0 ]]; then
		printf "\nRun again the script, process %d cann't be killed", $pid
		exit
	else
		printf "\n\nPROCESS %d:%s SUCCESFULLY KILLED\n", $pid $nameFind
	fi
fi
