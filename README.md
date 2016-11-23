# GTMBase64
GTMBase64 , the lib always use for decoding or encoding on Objective-C

## SPECIFICATION

> 1.base64String1 ,base64String2 and base64StringJPEG, these methods are  not accurate for base64 encoding or decoding

> 2.I recommended that you should use GTMBase64 for your NSData de/encode.


```

#import "UIData+custom.h"
#import <GTMBase64.h>

@implementation NSData (custom)

- (NSString *)base64String1:(NSData *)data
{
NSData * data = [data base64EncodedDataWithOptions:NSDataBase64Encoding64CharacterLineLength];
return [NSString stringWithUTF8String:[data bytes]];
}

- (NSString *)base64String2:(NSData *)data
{
return [data base64EncodedStringWithOptions:NSDataBase64Encoding64CharacterLineLength];
}

- (NSString *)base64String3:(NSData *)data
{
return [[NSString alloc] initWithData:[GTMBase64 encodeData:data] encoding:NSUTF8StringEncoding];
}

- (NSString *)base64StringJPEG:(NSData *)data
{
return [data base64EncodedStringWithOptions:NSDataBase64Encoding64CharacterLineLength];
}


@end
```
