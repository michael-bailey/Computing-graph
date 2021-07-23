# XPCService
XPCService is a inter process communication method created by apple.
It allows seperation of concerns epecially when it comes to permissions and security.

## Creating a service
Creating a service requires adding a new target in xcode.

This creates a few files one of which is a class protocol definition that is used to communucate witht your service in objective-c.

## Usage in app
### Creating connection to service

 To use the service from an application or other process, use NSXPCConnection to establish a connection to the service by doing something like this:

  
```objective-c
connectionToService = [[NSXPCConnection alloc] initWithServiceName:@"io.github.michael-bailey.ServerConnectionService"];

connectionToService.remoteObjectInterface = [NSXPCInterface interfaceWithProtocol:@protocol(ServerConnectionServiceProtocol)];

[connectionToService resume];
```
 ### Using the connection

Once you have a connection to the service, you can use it like this:

  

 \[\[\_connectionToService remoteObjectProxy\] upperCaseString:@"hello" withReply:^(NSString \*aString) {

 // We have received a response. Update our text field, but do it on the main thread.

 NSLog(@"Result string was: %@", aString);

 }\];

  

 And, when you are finished with the service, clean up the connection like this:

  

 \[\_connectionToService invalidate\];

\*/