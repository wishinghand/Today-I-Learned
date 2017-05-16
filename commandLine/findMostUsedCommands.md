# Find your most used commands

This counts the occurrences, filters out executables, and then ranks the top 10 most frequently used commands

`history | awk '{CMD[$2]++;count++;}END { for (a in CMD)print CMD[a] " " CMD[a]/count*100 "% " a;}' | grep -v "./" | column -c3 -s " " -t | sort -nr | nl |  head -n10`