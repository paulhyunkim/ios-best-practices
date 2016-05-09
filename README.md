This is intended as a personal reference for iOS best practices.

## Compile Time Optimizations

#### Objective-C
- [Remove unnecessary imports in headers](http://stackoverflow.com/questions/1479085/how-to-decrease-build-times-speed-up-compile-time-in-xcode/1479104#1479104)
- [Use forward declarations in headers and move imports to implementations](http://stackoverflow.com/questions/1479085/how-to-decrease-build-times-speed-up-compile-time-in-xcode/1479104#1479104)
```
@class ImportClass;
// not #import "ImportClass.h"

@interface MyClass : NSObject

+ (TypeFromImportClass)myMethod;

@end
```

#### Swift
- [Avoid using the following operations to improve compile time](https://medium.com/@RobertGummesson/regarding-swift-build-time-optimizations-fc92cdd91e31#.frvoiupvl):
  - Nil Coalescing Operator `??`
  - ArrayOfStuff + [Stuff]. Instead use `.append`
  - Ternary operator `(cond) ? (lhs) : (rhs)`
  - Casting CGFloat to CGFloat
  - Round()


## Run Time Optimizations
- [Improve table scrolling following the following guideline:](https://medium.com/ios-os-x-development/perfect-smooth-scrolling-in-uitableviews-fd609d5275a5#.y7jsqganf)
  - Don’t bind data at `cellForRowAtIndexPath:`. Instead use `willDisplayCell:forRowAtIndexPath:` method in the delegate of UITableView.
  - Calculate further cell heights faster, instead of relying on autolayout (although this really depends on if you want to sacrifice readability and conciseness for performance).
  - Reduce areas where iOS performs useless blending: don’t use transparent backgrounds.
  - Perform code optimizations to achieve balance of loading CPU & GPU.

## Styleguide

## Design Pattern


