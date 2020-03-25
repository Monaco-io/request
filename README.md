# Request

HTTP client for golang

## Features

- Make [http](https://golang.org/) requests from Golang
- Intercept request and response
- Transform request and response data

## Installing

go mod:

```bash
go get github.com/Monaco-io/request
```

## Example

### GET

```go
package main

import (
    "log"

    "github.com/Monaco-io/request"
)

func main() {
    client := request.Client{
        URL:    "https://baidu.com",
        Method: "GET",
        Params: map[string]string{"hello": "world"},
    }
    resp, err := client.Do()

    log.Println(string(resp), err)
}
```

### POST

```go
package main

import (
    "log"

    "github.com/Monaco-io/request"
)

func main() {
    client := request.Client{
        URL:    "https://baidu.com",
        Method: "POST",
        Params: map[string]string{"hello": "world"},
        Body:   []byte(`{"hello": "world"}`),
    }
    resp, err := client.Do()

    log.Println(string(resp), err)
}
```

## License

[MIT](LICENSE)
