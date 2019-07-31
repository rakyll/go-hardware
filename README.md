# Go + hardware

This repo is a directory of tools, packages and tutorials to let
you introduce Go in your hardware projects.

## Why Go?

* Go can target platforms and architectures that are primarily in the scope of non-real time embedded operating systems.
    - ARMv5, ARMv6, ARMv7 and ARMv8 support for Linux
    - ARMv7, ARMv8, x86 support for Android
    - Experimental OpenWRT

* Out-of-the-box cross compilation story.
    - E.g. Run `GOOS=linux GOARCH=arm go build` to build a binary for ARM/linux boards from a Mac or Windows machine. No other configuration is required.

* Built-in concurrency primitives in Go is making it easier to write concurrent programs.
    - Strong advantage in implementing hardware controllers.
    - Strong advantage in implementing networking devices.

* Go is garbage collected language but the garbage collector footprint has been improved significantly since Go 1.4. The pause times are being targetted to be 10ms or less even with large heaps and is not a significant disadvantage on non-real time operating systems -- the preemptive nature of the OS scheduler is more of a major problem than pause times.

* Go's network stack is high quality and maintained well. Networking is a core component in IoT.

* Go provides out-of-the-box HTTP, HTTPS and HTTP/2 client/server implementations.
    - Standard library might be missing higher level implementations for P2P protocols, but the community works to fill that gap.
    - Community is also investing time to implement newer IoT-targeting networking protocols such as COAP.

* Writing C bindings in Go is very trivial with cgo unlike other high level programming languages like Python and Java. It is so much easier to depend on an existing C/C++ library from the Go context.
    - E.g. [portmidi](https://github.com/rakyll/portmidi/blob/master/portmidi.go) bindings. See the source code to see how you can mix and match Go and C code in the same Go file.

* C-like syntax enables the existing IoT/embedded programmers (mostly fluent in C) to read and write Go without much knowledge of the language.

* Go programs compile to static binaries and doesn’t require a runtime on the host (e.g. a VM). Deployment is copy/pasting a binary.

* Go had strong community figures who worked on the hardware aspects from the early days.
    - Gobot made its debut at the first GopherCon.
    - There are numerous libraries and frameworks around hardware and robotics already contributed by the community. A list can be found at go-hardware.

* Go is efficient, fast and has low memory footprint.

* Code reuse between server and client (connected device or mobile).
    - E.g. gRPC Go is working out of the box on servers, Android, iOS and embedded Linux.


## Tutorials

* (Go 1.5 and above) [Cross compilation guide](https://medium.com/@rakyll/go-1-5-cross-compilation-488092ba44ec)
* (Go 1.4 and below) [Cross compilation guide](http://dave.cheney.net/2013/07/09/an-introduction-to-cross-compilation-with-go-1-1)
* [Go on ARM tips, known issues and success stories](https://github.com/golang/go/wiki/GoArm)

## Packages

### Controllers
* [devices](https://github.com/goiot/devices) - A repository of high-level device/sensor packages for Go.
* [gobot](http://gobot.io/) - High level Go package with a variety of platform APIs to talk to popular drivers such as GPIO on Arduino and Raspberry Pi, Leap Motion or Pebble.
* [go-gpio](https://github.com/stianeikeland/go-rpio) - GPIO for Go, doesn't require cgo.
* [embd](http://embd.io/) - Embedded programming framework for Go.
* [fadecandy](https://github.com/scanlime/fadecandy) - Dithering OPC-based LED controller
* [godrone](http://godoc.org/github.com/felixge/godrone/) - High level Parrot AR Drone 2.0 framework written in Go.
* [launchpad](https://github.com/rakyll/launchpad) - High level controller library for Novation Launchpad.
* [littlebits](https://github.com/rakyll/littlebits) - littleBits controller for Go. It requires [USB I/O](http://littlebits.cc/bits/usb-io) module.
* [piCamera](https://github.com/technomancers/piCamera) - Capture the stream of Images for a Raspberry Pi Camera in GoLang
* [hwio](https://github.com/mrmorphic/hwio) - Hardware library for ARM boards such as Raspberry Pi and BeagleBone, loosely based on Arduino.
* [go-lepton](https://github.com/maruel/go-lepton) - Streams images taken on a FLIR Lepton connected to a Raspberry Pi SPI port to over via WebSockets via embedded HTTP server.
* [go-embedded](https://github.com/SpaceLeap/go-embedded) - Embedded Linux support for I2C, SPI, PWM, GPIO, ADC
* [go-beaglebone](https://github.com/SpaceLeap/go-beaglebone) - Go package for the BeagleBone open source hardware
* [go-mavlink](https://github.com/SpaceLeap/go-mavlink) - MAVLink protocol implementation for Go (MAVLink is used to control drones)
* [joystick](https://github.com/SimulatedSimian/joystick) - a polled API to read the state of an attached joystick.
* [emgo](https://github.com/ziutek/emgo) - Go-like language for programming embedded systems (e.g. STM32 MCU).
* [go-rpi-rgb-led-matrix](https://github.com/mcuadros/go-rpi-rgb-led-matrix) - Controlling up to three chains of 32x32 or 16x32 RGB LED displays using Raspberry Pi GPIO
* [go-rpi-ws281x](https://github.com/mcuadros/go-rpi-ws281x) - Go bindings for Raspberry Pi PWM library for WS281X LEDs Edit
* [ghw](https://github.com/jaypipes/ghw) - Golang hardware discovery/inspection library
* [sysinfo](https://github.com/zcalusic/sysinfo) - A pure Go library providing Linux OS / kernel / hardware system information.


### Signal processing, computer vision, graphics, media
* [go-gl](https://github.com/go-gl) - OpenGL bindings for Go.
* [go-opc](https://github.com/kellydunn/go-opc) - Open Pixel Control bindings for Go.
* [go-opencv](https://github.com/lazywei/go-opencv) - OpenCV bindings for Go.
* [go-sox](https://github.com/krig/go-sox) - SoX bindings for Go.
* [portaudio](https://code.google.com/p/portaudio-go/) - PortAudio bindings for Go.
* [portmidi](https://github.com/rakyll/portmidi) - PortMidi bindings for Go.
* [go-osc](https://github.com/hypebeast/go-osc) - Open Sound Control (OSC) bindings for Go.
* [openvg](https://github.com/ajstarks/openvg) - 2D Graphics library wrapping the OpenVG API
* [lirc](https://github.com/chbmuc/lirc) - Go Client for Linux Infra-red Remote Control. Allows sending and receiving IR commands.
* [gocv](https://gocv.io) - OpenCV 3+ bindings for Go. Also supports OpenVINO.

### Networking, peripheral communications
* [mdns](https://github.com/hashicorp/mdns) - mDNS server and client implementation in Go. Multicast DNS can be used to discover services and message on the local network without the use of an authoritative DNS server.
* [gatt](https://github.com/paypal/gatt) - Provides a Bluetooth Low Energy GATT implementation.
* [go.hid](https://github.com/GeertJohan/go.hid) - Provides communication with USB Human Interface Devices.
* [goble](https://github.com/MarinX/goble) - Bluetooth Low Energy (HM10) module for Go
* [serial](https://github.com/tarm/serial) - Serial Port Communication Package for Go
* [firmata](https://github.com/kraman/go-firmata) - Firmata client for Go
* [periph](https://periph.io/) - Peripherals I/O in Go
* [go-ckb](https://gitlab.com/dnaf/go-ckb) - Corsair ckb-daemon communication in Go
* [ble](https://github.com/go-ble/ble) - Bluetooth Low Energy communication wrapper for Linux/macOS.

### Mobile (Go 1.5 or above)
* [Native applications (Android and iOS)](https://github.com/golang/go/wiki/Mobile#native-applications)
* [SDK applications](https://github.com/golang/go/wiki/Mobile#sdk-applications-and-generating-bindings)

Contributions are welcome, please fork and open a PR if you see
a missing package, tutorial, etc.
