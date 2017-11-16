# qclient
Qiniu auth client with ak/sk, you can access all qiniu services over http protocol.

## Usage

```
package main

import (
	"fmt"
	"net/http"
	"time"

	"github.com/songjiayang/qclient"
)

func main() {
	client := qclient.New(qclient.NewAccessKey("ak", "sk"))
	body, err := client.Send(http.MethodGet, "http://xxxx", "application/json", 30*time.Second, nil)

	fmt.Println(body)
	fmt.Println(err)
}
```

Note: if response code/200 != 1 it will raise a error.
