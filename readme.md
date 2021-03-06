# localhttpproxy

## install

```
npm i -g localhttpproxy
```

## command line

```
> lhp --help
Usage: lhp
    status
    server
    request --file [filepath]


Options:
  --version   Show version number                                      [boolean]
  -h, --help  Show help                                                [boolean]
```

```
> macns --help
Usage: macns
    --port [proxy port]
    --host [proxy host]
    --on   [turn global proxy on]
    --off  [turn global proxy off]


Options:
  --version   Show version number                                      [boolean]
  -h, --help  Show help                                                [boolean]
```

## lhp config example

```json
{
  "proxy": {
    "host": {
      "127.0.0.1:8080": [{
        "pathReg": "^/api",
        "targetHost": "127.0.0.1:5000"
      }],
      "127.0.0.1:8081": [{
        "pathReg": "^/api",
        "targetHost": "127.0.0.1:7788"
      }],
      "127.0.0.1:9000": [{
        "pathReg": "^/api",
        "targetHost": "127.0.0.1:4000"
      }],
      "127.0.0.1:9111": [{
        "pathReg": "^/api",
        "targetHost": "127.0.0.1:9200"
      }]
    }
  },
  "store": {
    "host": {
      "a.com": [{
        "url": "/dir1",
        "pathReg": "^/api",
        "fileNameRule": "time"
      }],
      "127.0.0.1:8080": [{
        "url": "/dir2",
        "pathReg": "^/api",
        "fileNameRule": "time"
      }]
    }
   }
}
```
