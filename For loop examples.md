# For loop examples
## Bash 
### URL: https://www.jesusninoc.com/2016/01/02/for-loop-examples/
```Shell
#Important:
#Set the script to be executable and run the script

#Example list of values
i=1
for num in One Two Three Four
do
echo "Number $((i++)) : $num"
done

#Example values in a variable
i=1
numbers="One Two Three Four"
for num in $numbers
do
echo "Number $((i++)) : $num"
done

#Example use the output of any Linux command
i=1
for num in `cat ./numbers.txt`
do
echo "Number $((i++)) : $num"
done

#Example C for loop syntax
for (( i=1; i <= 10; i++ ))
do
echo "Number $i"
done

#Example infinite for loop
i=1;
for (( ; ; ))
do
echo "Number $((i++))"
done

#Example range of numbers using brace expansion
for num in {1..10}
do
echo "Number $num"
done

```
