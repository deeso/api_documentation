# Status of a hash
```
POST /
```
| Item              | Value                                                 | 
| ----------------- | ----------------------------------------------------- |
| Method            | `POST`                                                |
| Endpoint          | `/`                                                   |
| Description       | Whether or not a given hash is known and its intent.  |
| Authentication    | `None`                                                |


## Parameters

| Item        | Type            | Description                                           | 
| ----------- | --------------- | ----------------------------------------------------- |
| `hash`      | List or String  | (Required) One or more hashes to look up. Limit: 500  |
| `api_key`   | String          | API Key                                               |

## Returns

In addition to the standard values returned by a [result dictionary](https://github.com/hashdd/api_documentation/blob/master/general/result.md), responses from this endpoint also contain:

| Item                  | Description                               | 
| --------------------- | ----------------------------------------- |
| `known_level`         | The [known level](https://github.com/hashdd/api_documentation/blob/master/general/verdict.md) of the query. |

## Example
```
curl -d 'hash=838DE99E82C5B9753BAC96D82C1A8DCB' https://api.hashdd.com/
```

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

