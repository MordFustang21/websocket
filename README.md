# Supernova Websocket
[![GoDoc](https://godoc.org/github.com/MordFustang21/supernova?status.svg)](https://godoc.org/github.com/MordFustang21/websocket)
[![Go Report Card](https://goreportcard.com/badge/github.com/mordfustang21/supernova)](https://goreportcard.com/report/github.com/mordfustang21/websocket)
[![Build Status](https://travis-ci.org/MordFustang21/websocket.svg?branch=master)](https://travis-ci.org/MordFustang21/websocket)

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