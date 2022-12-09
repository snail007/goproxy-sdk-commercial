# goproxy-sdk-commercial
goproxy sdk commercial edition

[Download](https://github.com/snail007/goproxy-sdk-commercial/releases)  

The following platforms are supported:
- Android, `.arr` library
- IOS, `.framework` library
- Windows, `.dll` library
- Linux, `.so` library
- MacOS, `.dylib` library

## Android SDK

### Example

#### 1. Importing packages

```java
import snail007.goproxy.sdk.Sdk;
```

#### 2. Start a service

```java
String serviceID="http01";// serviceID is globally unique.
String serviceArgs="http -p :8080";
Sdk.setAuthCode("xxx");//xxx auth code is purchased from platform 
String err=Sdk.start(serviceID,serviceArgs);
if (!err.isEmpty()){
    // Failed to start
    System.out.println("start fail,error:"+err);
}else{
    // Successful launch
}
```

#### 3. Stop service

```java
String serviceID="http01";
Proxy.stop(serviceID);
// Stop over.

```

When the service starts,if there is a service running with the same ID, then the previous service will be stopped and the previous service will be overwritten later.  

So make sure that the first ID parameter is unique every time you start the service.  

The specific usage and parameters of these services can be found in [proxy manual](https://github.com/snail007/goproxy/blob/master/README.md) 
# Important
The SDK args parameter does not support the `--daemon` and `--forever`.

