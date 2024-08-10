# OpenSearch Read Only Index

<img width="85" alt="map-user" src="https://img.shields.io/badge/views-1414-green"> <img width="125" alt="map-user" src="https://img.shields.io/badge/unique visits-950-green">

If you prefer to watch a video instead of reading the instructions below, check out the link below

YouTube video - https://youtu.be/45T49W9DHo4

## Overview
OpenSearch indices can be set to read only ie. all write requests will throw an exception and be blocked. There are multiple reasons why you would want to make an index read only. One reason is before running certain back end operations such as a force merge it is recommended to make an index read only.

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

<img width="800" alt="cat_indicies_1" src="https://github.com/ev2900/OpenSearch_Read_Only_Index/blob/main/README/read_only_true.PNG">

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

<img width="800" alt="cat_indicies_1" src="https://github.com/ev2900/OpenSearch_Read_Only_Index/blob/main/README/read_only_false.PNG">
