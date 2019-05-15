---
title: Linux
category: CLI
layout: 2017/sheet
updated: 2019-5-15

---

## Options

### Options

```bash
-a    # 显示全部文件
-d    # 显示目录的信息
-l    # 显示详细信息
```

```bash
-v           # --verbose
-vv          # Even more verbose
```

```bash
-I           # --head: headers only
```

### Request

```bash
-X POST          # --request
```

### Data

```bash
-d 'data'    # --data: HTTP post data, URL encoded (eg, status="Hello")
-d @file     # --data via file
-G           # --get: send -d data via get
```

### Headers

```bash
-A <str>         # --user-agent
-b name=val      # --cookie
-b FILE          # --cookie
-H "X-Foo: y"    # --header
--compressed     # use deflate/gzip
```

### SSL

```bash
    --cacert <file>
    --capath <dir>
```

```bash
-E, --ecrt <cert>     # --ecrt: Client cert file
    --cert-type       # der/pem/eng
-k, --insecure        # for self-signed certs
```

## Examples

{: .-one-column}

```bash
# Post data:
curl -d password=x http://x.com/y
```

```bash
# Auth/data:
curl -u user:pass -d status="Hello" http://twitter.com/statuses/update.xml
```

```bash
# multipart file upload
curl -v -include --form key1=value1 --form upload=@localfilename URL
```