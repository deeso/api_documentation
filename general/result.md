# Results 

All API results are wrapped in a dictionary which contains at minimum, a `result` key (top level). All other keys within the dictionary are named after the queried hashes. A `result` key also exists within each hash key (hash level). The `result` key has a slightly different meaning depending on the level 

| Location      | Description                               |
| ------------  | ----------------------------------------- | 
| Top level     | The result of the overall API query.      | 
| Hash level    | The result of the individual hash query.  | 

## Return Values

The value of result may be:

| Value         | Level     | Description                           |
| ------------- | --------- | ------------------------------------- |
| `SUCCESS`     | top       | The query succeeded.                  |
| `FAILURE`     | top       | The query failed.                     |
| `SUCCESS`     | hash      | The hash was found.                   |
| `NOT_FOUND`   | hash      | The hash was not found.               |


In the case of `FAILURE` a `message` key may also be present, defining the reason for the failure. 



# Examples

## Successful Query and Found Hash 
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

## Successful Query and Unknown Hash
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





