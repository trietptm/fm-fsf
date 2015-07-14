# Using a wordlist? #

```

FSF.exe -m wordlist -o "c:\wordlists\sqli.txt" -u http://www.example.com/sql.asp?id=[FUZZ]

```

# Fuzzing POST parameters #

```

FSF.exe -m wordlist -o "c:\wordlists\sqli.txt" -u http://www.example.com/sql.asp  -p "id=[FUZZ]"

```


# What the hell is a plug-in based fuzzer? #

Basically every attack type such as numeric, wordlist based is a separate DLL which implements IReader interface. This means you can write a new DLL in any .NET language then drop it do same folder and do a really complicated fuzzing.


FSF ships with only 2 plug-ins (generally referred as modules).
  * Integer Module
  * Wordlist