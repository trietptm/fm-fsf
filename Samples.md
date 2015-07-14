I have to agree that it's not that freakin' easy. It gets complicated but that's the life for you.

# Simple Integer Based Fuzzing #

From 1 to 100. Saves RegEx capture ".**" output to "c:\out\out.txt". It won't show HTTP Status code 200.**

```

fsf.exe -u "http://www.example.com/SQLInjection-Numeric/?p=[FUZZ]" -m integer -o 1-100 --capture-output "C:\out\out.txt" -c .* -h 200

```


# Data Scraping #

This scrapes all projects with a "php" tag in google code and will save them in the c:\out\gc.txt

```

fsf.exe -u "http://code.google.com/hosting/search?q=php&filter=1&start=[FUZZ]" -m integer -o 0-3000-10, --capture-output "C:\out\gc.txt" -c "href=./p/([^/]*)/." --capture-group 1 --capture-template "{1}" --match-template "{0}{1}" -t 10

```

# Basic Auth Brute Forcing #
```
fsf.exe -u "http://example.com:8001/Basic-Auth/" --username [FUZZ] --password [FUZZ2] -m wordlist -o "C:\Wordlist\users.txt" -f
```

Usernames and passwords should ":" separated in the wordlist.

```
user1:pass1
user2:pass2
...
```

Same applies to all 2 parameter fuzzing attacks.

Use `-h 401` to hide unsuccessful authentication attempts.