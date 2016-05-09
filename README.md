This is intended as a personal reference for iOS best practices.

## Compile Time Optimizations

#### Objective-C
- Remove unnecessary imports in headers[*](http://stackoverflow.com/questions/1479085/how-to-decrease-build-times-speed-up-compile-time-in-xcode/1479104#1479104)
- Use forward declarations in headers and move imports to implementations[*](http://stackoverflow.com/questions/1479085/how-to-decrease-build-times-speed-up-compile-time-in-xcode/1479104#1479104)
```
@import "ImportClass.h"
// not #import "ImportClass.h"

@interface MyClass : NSObject

+ (TypeFromImportClass)myMethod;

@end
```

#### Swift
- Avoid using the following operations to [improve compile time](https://medium.com/@RobertGummesson/regarding-swift-build-time-optimizations-fc92cdd91e31#.frvoiupvl):
  - Nil Coalescing Operator `??`
  - ArrayOfStuff + [Stuff]. Instead use `.append`
  - Ternary operator `(cond) ? (lhs) : (rhs)`
  - Casting CGFloat to CGFloat
  - Round()


## Run Time Optimizations
- [Improving table scrolling](https://medium.com/ios-os-x-development/perfect-smooth-scrolling-in-uitableviews-fd609d5275a5#.y7jsqganf)


## Styleguide


