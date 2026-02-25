# Basics of AWK
- Command Structure
- Options and Selection Criteria
- Action Block in Braces
- Input and Output Handling

## Implementation
```sh
[hakan@archlinux Bash]$ mkdir AOB && cd $_
[hakan@archlinux AOB]$ mkdir awk && cd $_
[hakan@archlinux awk]$ vim automate.sh
[hakan@archlinux awk]$ chmod +x automate.sh 
[hakan@archlinux awk]$ ./automate.sh 
[hakan@archlinux awk]$ ls
automate.sh  data.txt
[hakan@archlinux awk]$ cat data.txt 
Brand   Model   RAM
Apple   MacBook  32
Apple   iPad     16
Dell    XPS      32
Dell    Inspiron 128
Lenovo  ThinkPad 128
Lenovo  Yoga     256
Apple   MacBook  64
[hakan@archlinux awk]$ nvim docs.md
[hakan@archlinux awk]$ awk '{print}' data.txt 
Brand   Model   RAM
Apple   MacBook  32
Apple   iPad     16
Dell    XPS      32
Dell    Inspiron 128
Lenovo  ThinkPad 128
Lenovo  Yoga     256
Apple   MacBook  64
[hakan@archlinux awk]$ awk '{print $1, $2}' data.txt 
Brand Model
Apple MacBook
Apple iPad
Dell XPS
Dell Inspiron
Lenovo ThinkPad
Lenovo Yoga
Apple MacBook
[hakan@archlinux awk]$ awk '$3 >= 64 {print $0}' data.txt 
Brand   Model   RAM
Dell    Inspiron 128
Lenovo  ThinkPad 128
Lenovo  Yoga     256
Apple   MacBook  64
[hakan@archlinux awk]$ awk 'NR > 1 {print}' data.txt 
Apple   MacBook  32
Apple   iPad     16
Dell    XPS      32
Dell    Inspiron 128
Lenovo  ThinkPad 128
Lenovo  Yoga     256
Apple   MacBook  64
[hakan@archlinux awk]$ awk 'NR == 3 {print}' data.txt 
Apple   iPad     16
[hakan@archlinux awk]$ awk '/Apple/ {print}' data.txt 
Apple   MacBook  32
Apple   iPad     16
Apple   MacBook  64
[hakan@archlinux awk]$ awk 'NR>1 {sum+=$3; count++} END {print "Average Ram:", sum/count}' data.txt 
Average Ram: 93.7143
[hakan@archlinux awk]$ awk 'NR>1 {print "Brand:", $1, "- Model:" $2}' data.txt 
Brand: Apple - Model:MacBook
Brand: Apple - Model:iPad
Brand: Dell - Model:XPS
Brand: Dell - Model:Inspiron
Brand: Lenovo - Model:ThinkPad
Brand: Lenovo - Model:Yoga
Brand: Apple - Model:MacBook
[hakan@archlinux awk]$ awk 'BEGIN {print "Brand   Model   RAM"} NR>1 {printf "%-8s %-10s %2d\n", $1, $2, $3}' data.txt 
Brand   Model   RAM
Apple    MacBook    32
Apple    iPad       16
Dell     XPS        32
Dell     Inspiron   128
Lenovo   ThinkPad   128
Lenovo   Yoga       256
Apple    MacBook    64
```
