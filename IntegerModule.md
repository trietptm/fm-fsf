# Options #

StartNumber-EndNumber[-Increaser][-Format]

# Example #

1 to 1000

```
FSF.exe -m integer -o 1-1000 -u http://example.com/userid/[FUZZ]/
```

Output will be look like:

```
http://example.com/userid/1/
http://example.com/userid/2/
http://example.com/userid/3/
.....
```



# Example 2 #

1 to 100 increases by 20

```
FSF.exe -m integer -o 0,100,20 -u http://example.com/list/?startindex=[FUZZ]
```

Output will be look like:

```
http://example.com/list/?startindex=0
http://example.com/list/?startindex=20
http://example.com/list/?startindex=40
http://example.com/list/?startindex=60
.....
```

# Example 3 / Using formatting #

1 to 100 increases by 20 and pad numbers

```
FSF.exe -m integer -o 0-1000-1-0000 -u http://example.com/list/?startindex=[FUZZ]
```

Output will be look like:

```
http://example.com/list/?startindex=0001.pdf
http://example.com/list/?startindex=0002.pdf
http://example.com/list/?startindex=0003.pdf
http://example.com/list/?startindex=0004.pdf
.....
http://example.com/list/?startindex=0124.pdf
.....
```

Formatting internally uses .NET's `Integer.ToString([Your Format])`, so you can do many eccentric stuff with it.