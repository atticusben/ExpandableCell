# ExpandableCell
[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![Version](https://img.shields.io/cocoapods/v/ExpandableCell.svg?style=flat)](http://cocoapods.org/pods/ExpandableCell)
[![Carthage Compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://github.com/younatics/YNExpandableCell/blob/master/LICENSE)
[![Platform](https://img.shields.io/cocoapods/p/YNExpandableCell.svg?style=flat)](http://cocoapods.org/pods/ExpandableCell)
[![Swift 3.0](https://img.shields.io/badge/Swift-3.0-orange.svg?style=flat)](https://developer.apple.com/swift/)
![iOS 8.0+](https://img.shields.io/badge/iOS-8.0%2B-blue.svg)

## Intoduction
Fully refactored [YNExapnadableCell](https://github.com/younatics/YNExpandableCell) with more concise, bug free. Easiest usage of expandable & collapsible cell for iOS, written in Swift 3. You can customize expandable `UITableViewCell` whatever you like. `ExpandableCell` is made because `insertRows` and `deleteRows` is hard to use. Just inheirt `ExpandableDelegate`

![demo](Images/ExpandableCell.gif)

## Usage
### Basic
```swift
import ExpandableCell
```

Make `ExpandableTableView` in Storyboard or in code
```swift
@IBOutlet var tableView: ExpandableTableView!
```

Inherit `ExpandableDelegate`
```swift
class ViewController: UIViewController, ExpandableDelegate 
```

Set delegate
```swift
tableView.expandableDelegate = self
```

Set required `ExpandableDelegate` method.

#### Key two methods
| Required Delegate | return type | Explanation |
| ----------------- | ----------- | ----------- |
| `func expandableTableView(_ expandableTableView: ExpandableTableView, expandedCellsForRowAt indexPath: IndexPath) -> [UITableViewCell]?` | `[UITableViewCell]?` | `ExpandableDelegate` key method to get expandable cells |
| `func expandableTableView(_ expandableTableView: ExpandableTableView, heightsForExpandedRowAt indexPath: IndexPath) -> [CGFloat]?` | `[CGFloat]?` | `ExpandableDelegate` key method to get expandable cells's height |

#### UITableViewDelegate, UITableViewDataSource

| Required Delegate | return type |
| ----------------- | ----------- |
| `func expandableTableView(_ expandableTableView: ExpandableTableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell` | `UITableViewCell` |
| `func expandableTableView(_ expandableTableView: ExpandableTableView, numberOfRowsInSection section: Int) -> Int` | `Int` |
| `func expandableTableView(_ expandableTableView: ExpandableTableView, heightForRowAt indexPath: IndexPath) -> CGFloat` | `CGFloat` |

### Advanced
| Optional Delegate | return type | Explanation |
| ----------------- | ----------- | ----------- |
| `didSelectRowAt` | - | UITableViewDelegate |
| `heightsForExpandedRowAt` | `[CGFloat]?` | `ExpandableDelegate` key method to get expandable cells's height |

Set optional `ExpandableDelegate` method.
```swift
func expandableTableView(_ expandableTableView: ExpandableTableView, didSelectRowAt indexPath: IndexPath)

func expandableTableView(_ expandableTableView: ExpandableTableView, expandedCell: UITableViewCell, didSelectExpandedRowAt indexPath: IndexPath)

func expandableTableView(_ expandableTableView: ExpandableTableView, didSelectExpandedRowAt indexPath: IndexPath)

func expandableTableView(_ expandableTableView: ExpandableTableView, titleForHeaderInSection section: Int) -> String?

func expandableTableView(_ expandableTableView: ExpandableTableView, heightForHeaderInSection section: Int) -> CGFloat

func expandableTableView(_ expandableTableView: ExpandableTableView, viewForHeaderInSection section: Int) -> UIView?
    
func numberOfSections(in expandableTableView: ExpandableTableView) -> Int

func expandableTableView(_ expandableTableView: ExpandableTableView, willDisplay cell: UITableViewCell, forRowAt indexPath: IndexPath)
    
func expandableTableView(_ expandableTableView: ExpandableTableView, willDisplayHeaderView view: UIView, forSection section: Int)
    
func expandableTableView(_ expandableTableView: ExpandableTableView, willDisplayFooterView view: UIView, forSection section: Int)
```

### Customize
Inherit `ExpandableCell` when you need arrow effect or change arrow image

```swift
open class ExpandableCell: UITableViewCell {
    open var arrowImageView: UIImageView!
}
```

Use close and open all function
```Swift
tableView.closeAll()
tableView.openAll()
```

Set tableview insert animation
```Swift
tableView.animation = .automatic
```

Make protocols in `ExpandableDelegate` if you need or make pull request to me :)

## Requirements
`ExpandableCell` written in Swift 3. Compatible with iOS 8.0+

## Installation

### Cocoapods

ExpandableCell is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'ExpandableCell'
```
### Carthage
```
github "younatics/ExpandableCell"
```

## References
#### Please tell me or make pull request if you use this library in your application :) 

## Author
[younatics](https://twitter.com/younatics)
<a href="http://twitter.com/younatics" target="_blank"><img alt="Twitter" src="https://img.shields.io/twitter/follow/younatics.svg?style=social&label=Follow"></a>

## License
ExpandableCell is available under the MIT license. See the LICENSE file for more info.
