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

* (Go 1.5 and above) [Cross complation guide](https://medium.com/@rakyll/go-1-5-cross-compilation-488092ba44ec)
* (Go 1.4 and below) [Cross complation guide](http://dave.cheney.net/2013/07/09/an-introduction-to-cross-compilation-with-go-1-1)
* [Go on ARM tips, known issues and success stories](https://github.com/golang/go/wiki/GoArm)

## Packages

### Controllers, robotics, etc
* [gobot](http://gobot.io/) - High level Go package with a variety of platform APIs to talk to popular drivers such as GPIO on Arduino and Raspberry Pi, Leap Motion or Pebble.
* [go-gpio](https://github.com/stianeikeland/go-rpio) - GPIO for Go, doesn't require cgo.
* [embd](http://embd.io/) - Embedded programming framework for Go.
* [fadecandy](https://github.com/scanlime/fadecandy) - Dithering OPC-based LED controller
* [godrone](http://godoc.org/github.com/felixge/godrone/) - High level Parrot AR Drone 2.0 framework written in Go.
* [launchpad](https://github.com/rakyll/launchpad) - High level controller library for Novation Launchpad.
* [littlebits](https://github.com/rakyll/littlebits) - littleBits controller for Go. It requires [USB I/O](http://littlebits.cc/bits/usb-io) module.
* [hwio](https://github.com/mrmorphic/hwio) - Hardware library for ARM boards such as Raspberry Pi and BeagleBone, loosely based on Arduino.
* [go-lepton](https://github.com/maruel/go-lepton) - Streams images taken on a FLIR Lepton connected to a Raspberry Pi SPI port to over via WebSockets via embedded HTTP server.
* [go-embedded](https://github.com/SpaceLeap/go-embedded) - Embedded Linux support for I2C, SPI, PWM, GPIO, ADC
* [go-beaglebone](https://github.com/SpaceLeap/go-beaglebone) - Go package for the BeagleBone open source hardware
* [go-mavlink](https://github.com/SpaceLeap/go-mavlink) - MAVLink protocol implementation for Go (MAVLink is used to control drones)

### Signal processing, computer vision, graphics, media
* [go-gl](https://github.com/go-gl) - OpenGL bindings for Go.
* [go-opc](https://github.com/kellydunn/go-opc) - Open Pixel Control bindings for Go.
* [go-opencv](https://github.com/lazywei/go-opencv) - OpenCV bindings for Go.
* [go-sox](https://github.com/krig/go-sox) - SoX bindings for Go.
* [portaudio](https://code.google.com/p/portaudio-go/) - PortAudio bindings for Go.
* [portmidi](https://github.com/rakyll/portmidi) - PortMidi bindings for Go.
* [go-osc](https://github.com/hypebeast/go-osc) - Open Sound Control (OSC) bindings for Go.
* [openvg](https://github.com/ajstarks/openvg) - 2D Graphics library wrapping the OpenVG API
* [lirc] (https://github.com/chbmuc/lirc) - Go Client for Linux Infra-red Remote Control. Allows sending and receiving IR commands.

### Networking, peripheral communications
* [mdns](https://github.com/hashicorp/mdns) - mDNS server and client implementation in Go. Multicast DNS can be used to discover services and message on the local network without the use of an authoritative DNS server.
* [gatt](https://github.com/paypal/gatt) - Provides a Bluetooth Low Energy GATT implementation.
* [go.hid](https://github.com/GeertJohan/go.hid) - Provides communication with USB Human Interface Devices.
* [goble](https://github.com/MarinX/goble) - Bluetooth Low Enery (HM10) module for Go
* [serial] (https://github.com/tarm/serial) - Serial Port Communication Package for Go

### Mobile

Contributions are welcome, please fork and open a PR if you see
a missing package, tutorial, etc.

