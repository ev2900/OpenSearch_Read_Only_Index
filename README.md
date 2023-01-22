# OpenSearch Read Only Index

OpenSearch indices can be set to read only ie. all write requests will throw and exception and be blocked. There are multiple reasons why you would want to make an index read only. One reason is before running certain back end operations such as a force merge it is recommended to make an index read only.

The instructions below demonstrate how to make an index read only and the enable writes again.

## Set an Index to Read Only

Running 

```
PUT sample-data/_settings
{
  "index": {
    "blocks.read_only": true
  }
} 
```

Will set the index **sample-data** to read only. After running the API call above if you try to write a document to the index you will receive an error

IMAGE 1

## Disable Read Only (ie. enable writes)

To re-enable writes or disable read only you can run the following API call

```
PUT sample-data/_settings
{
  "index": {
    "blocks.read_only": false
  }
} 
```

Once read only is false, you can again write data to the index

IMAGE 2
