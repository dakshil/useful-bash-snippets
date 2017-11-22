# useful-bash-snippets
#Contains useful bash snippets

#extract first line from file and get last value in line
line=$(head -n 1 filename)
last_in_line=($(echo $line | awk '{print $NF}'))               
echo "$line $last_in_line"

#get only real time of process execution in seconds
declare -a array=( $( { time process_command; } 2>&1 >/dev/null ))
real=($(echo ${array[1]} | awk -F'[ms]' '{print 60*$1+$2}'))
echo "$real

