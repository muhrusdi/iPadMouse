# iPad Mouse
An iOS app + server which allows you to use your iPad as a graphics tablet. Latency is minimal due to the use of WebSockets over a direct WiFi connection.

> TODO: Add Usage GIF

## Dependencies
Uses [StarScream](https://github.com/daltoniam/Starscream) as the WebSocket client, and [Zewo/WebSocketServer](https://github.com/Zewo/WebSocketServer) as the WebSocket server.

## Setup
### Client
To run the client application, you need Xcode 8 Beta 2. You also need to fetch the dependencies, `carthage bootstrap --no-build`. Then, the app should build on any iOS device (tested on iOS 10 iPad Pro).

### Server
To run the server, you need to be able to build code compatible with the 05-09 snapshot with the OSX SDK. For me, the following options work:

- Generate the Xcode project with `swift build -X` and open it using Xcode 7.3.1 with the 05-09 snapshot selected
- Have Xcode 8 Beta 1 selected using `xcode-select` and run `xcrun --sdk macosx swift build` in the command line

## Usage
Ensure that both of your devices are connected to the same WiFi network.

Replace the [`ip` constant](https://github.com/Danappelxx/iPadMouse/blob/master/ipad-mouse-ios/ViewController.swift#L14) with your mac's ip address in the local network. You can find this by running `ifconfig | grep netmask`. For my machine, it is `192.168.1.132`.

Run the iOS app on your device and wait for it to connect. Once connected, you can perform the following gestures:

- Single tap = left click
- Double tap = double left click
- Single tap + movement = move mouse
- Double tap + movement = move mouse with left click