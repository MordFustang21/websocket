# Supernova Websocket

Add websocket support for supernova/fasthttp

Example
```go
package main

import (
	"log"
	"github.com/MordFustang21/supernova"
)

func main() {
	s := supernova.Super()

	// Websocket example
	s.All("/ws", func(req *supernova.Request) {
        err := upgrader.Upgrade(req, func(conn *supernova.Conn) {
            conn.WriteMessage(supernova.TextMessage, []byte("Web socket success"))
        })

        if err != nil {
            println("Error upgrading connection")
        }
    })

	err := s.Serve(":8080")

	if err != nil {
		log.Fatal(err)
	}
}
```