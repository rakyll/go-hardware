# Go + hardware

This repo is a directory of tools, packages and tutorials to let
you introduce Go in your hardware projects.

## Why Go?

* Great tooling that comes with a strong cross compilation story.
* Builtin concurrency primitives in Go is making it easier to write
concurrent programs.
* Go runs on ARM boards. ARM boards are getting cheaper, making
it easier for production designs to include them. Higher-level
languages have more opportunities than ever on hardware projects.
* Go is garbage collected but you can still use it to write
non-realtime or networked controllers. There are plenty of
Go users who program their experimental drone flight control
software in Go, it's OK for prototyping.
* Go's network stack is maintained well. Standard library might
be missing higher level implementations for P2P protocols, but
the community works to fill that gap.
* Writing C bindings in Go is a pleasure with
[cgo](https://golang.org/cmd/cgo/).

## Tutorials

* [An introduction to cross compilation with Go](http://dave.cheney.net/2013/07/09/an-introduction-to-cross-compilation-with-go-1-1)
* [Go on ARM tips, known issues and success stories](https://github.com/golang/go/wiki/GoArm)

## Packages

### Controllers, robotics, etc
* [gobot](http://gobot.io/) - High level Go package with a variety of platform APIs to talk to popular drivers such as GPIO on Arduino and Raspberry Pi, Leap Motion or Pebble.
* [embd](http://embd.io/) - Embedded programming framework for Go.

### Signal processing, computer vision, graphics, media
* [go-gl](https://github.com/go-gl) - OpenGL bindings for Go.
* [go-opencv](https://github.com/lazywei/go-opencv) - OpenVM bindings for Go.
* [go-sox](https://github.com/krig/go-sox) - SoX bindings for Go.
* [portaudio](https://code.google.com/p/portaudio-go/) - PortAudio bindings for Go.
* [portmidi](https://github.com/rakyll/portmidi) - PortMidi bindings for Go.
* [go-osc](https://github.com/hypebeast/go-osc) - Open Sound Control (OSC) bindings for Go.

### Networking
* [mdns](https://github.com/hashicorp/mdns) - mDNS server and client implementation in Go. Multicast DNS can be used to discover services and message on the local network without the use of an authoritative DNS server.

### Mobile

Contributions are welcome, please fork and open a PR if you see
a missing package, tutorial, etc.

