## Command Substitution:  Sum 456

```
# fn=456
# a=`echo $fn  |cut -c 1`
# b=`echo $fn  |cut -c 2`
# c=`echo $fn  |cut -c 3`
# d=`expr $a + $b + $c`
# echo “sum of 456 is :” $d

```

##  program for addition and subtraction

```
echo "Enter a:"
read a
echo "Enter b:"
read b
sum=`expr $a + $b`
diff=`expr $a - $b`
prod=`expr $a \* $b`
quo=`expr $a / $b`
echo $sum
echo $diff
echo $prod
echo $quo

```
## multiple conditions in for loop

```
for g in 1 2 3
do
   for c in 123 456 789
   do
       if [[ ( "$g" -eq 1 && "$c" = "123" ) || ( "$g" -eq 2 && "$c" = "456" ) ]];       then 
echo "g = $g; c = $c; true"
      else
 echo "g = $g; c = $c; false"
       fi
  done
done


```


## program on while

```
    a=0;
 	while [ $a -lt 5 ];
	do
  	date
 	a=`expr $a + 1`
  	done

```

## Program on for loop


```
i=1
for day in Mon Tue Wed Thu Fri
do
echo "Weekday $((i++)) : $day"
done

```

## shell script with C snippet

```
#!/bin/bash
for (( c=1; c<=5; c++ ))
do
echo "Welcome $c times..."
done

```

##  shell script to execute to identify the count of word(user) in passwd file

```
#!/bin/bash
for f in /etc/*
do
if [ "${f}" == "/etc/passwd" ];  then
 c=$(grep -c User /etc/passwd)
 echo "Total  ${c} name defined in ${f}"
 break
fi
done

```

## Shell script to identify file or folder


```
#!/bin/bash
FILES="$@"
for f in $FILES
do
# if .bak backup file exists, read next file
if [ -f $f ]; then
 echo "It is a file"
 continue  # read next file 
fi
done


```
## shell script for function to add numbers

```
#!/bin/bash
#function to add two numbers
add()
{
x=$1
y=$2
echo -e "Number entered by u are: $x and $y"
echo "sum of $1 and $2 is `expr $x + $y` "
}

# main script
echo "enter first number"
read first
echo "enter second number"
read sec
#calling function
add $first $sec
echo "end of the script"

```


## Case with user inputs

```
#!/bin/bash
echo -n "Do you agree with this? [yes or no]: "
read yno
case $yno in
       [yY] | [yY][Ee][Ss] )
               echo "Agreed"
               ;;

       [nN] | [n|N][O|o] )
               echo "Not agreed, you can't proceed the installation";
               exit 1
               ;;
       *) echo "Invalid input"
           ;;
esac


```