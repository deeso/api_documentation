# Verdicts 

Verdicts are made on all files and hashes within hashdd. These verdicts are described through the `known_level` and `intent` groupings. 

## Known Level

Describes whether or not a hash is known to hashdd and, in some cases, if that hash represents a file with a known good or bad intent. Known levels are described in the following table:

| Value         | Description                               |
| ------------- | ----------------------------------------- |
| `Good`        | The hash is known to hashdd and represents a file known to have a good intent.  |
| `Bad`         | The hash is known to hashdd and represents a file known to have a bad intent.   |
| `Unknown`     | The hash is unknown to hashdd.            |
| Numerical     | The hash is known to hashdd and users have voted on its intent (See below). |


## Intent

Attempts to describes the intent of the file at time of creation. Files with a `Good` intent are those which are included as part of standard operating system distributions, standard product releases, debugging tools, and even information gathering tools. `Good` files may include files which are used by attackers. Files with a `Bad` intent are those which were expressly developed with malice such as malware, trojans, exploits, etc... 

### Numerical Intent
hashdd also allows for users to vote on intent, with postive votes being `Good`, negative votes being `Bad` and a vote of zero being unknown.  


# Examples

## Known Good
```
{
    "838DE99E82C5B9753BAC96D82C1A8DCB": 
        {
            "known_level": "Good", 
            "result": "SUCCESS"
        }, 
    "result": "SUCCESS"
}
```

## Known and Voted as Good
```
{
    "A228F0E506897539E3B38A3CDB3E33E7": 
        {
            "known_level": 1, 
            "result": "SUCCESS"
        }, 
    "result": "SUCCESS"
}
```

## Unknown Hash
```
{
    "838DE99E82C5B9753BAC96D82C1A8DCA": 
        {
            "known_level": "Unknown", 
            "result": "NOT_FOUND"
        },
        "result": "SUCCESS"
}
```


