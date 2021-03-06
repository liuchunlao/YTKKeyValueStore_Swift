YTKKeyValueStore
==========

objc version ：https://github.com/yuantiku/YTKKeyValueStore

![License MIT](https://go-shields.herokuapp.com/license-MIT-blue.png)


## Requirements

- iOS 7.0+ 
- Xcode 6.3


## Usage 

```swift
import YTKKeyValueStore
```

### YTKKeyValueStore

```swift
var store = YTKKeyValueStore("test.db")   // create or open the key-value store

store.createTable("User")    // create table

let table = store["User"]      // get table (YTKTable)

store.dropTable("User")    // drop table
```

### YTKTable

```swift
let isExists = table.isExists

table.put( "name" <- ("sgxiang" as NSString) )     // put value("sgxiang") for key("name") into table , support string,number,dictionary,array


let objct = table.get("name")    // get object with key , return YTKObject?
let item = table.getItem("name")   // get item with key ,return YTKItem?
let allItems = table.getAllItems()  // get all item with key , return  [YTKItem]?


table.clear()  // clear table
table.delete("name1","name2")   // delete row where key == "name1" and "name2"
table.deletePreLike("name")   // delete row where key pre like "name"
```

### YTKItem

```
itemId       :   itemKey
itemObject   :   itemValue , is json string
createdTime  :   item created time
```
### YTKObject

```
objectValue       :     return  AnyObject?
stringValue       :     return  String?
numberValue       :     return  NSNumber?
dictionaryValue   :     return  Dictionary<String , AnyObject>?
arrayValue        :     return  Array<AnyObject>?
```

## Installation

### Embedded Framework

- Add YTKKeyValueStore as a submodule by opening the Terminal, cd-ing into your top-level project directory, and entering the following command:

```
$ git submodule add https://github.com/Sgxiang/YTKKeyValueStore_Swift.git
```
- Open the YTKKeyValueStore folder, and drag YTKKeyValueStore.xcodeproj into the file navigator of your app project.

- In Xcode, navigate to the target configuration window by clicking on the blue project icon, and selecting the application target under the "Targets" heading in the sidebar.

- Ensure that the deployment target of YTKKeyValueStore.framework matches that of the application target.

- In the tab bar at the top of that window, open the "Build Phases" panel.
Expand the "Target Dependencies" group, and add YTKKeyValueStore.framework.

- Click on the + button at the top left of the panel and select "New Copy Files Phase". Rename this new phase to "Copy Frameworks", set the "Destination" to "Frameworks", and add YTKKeyValueStore.framework.

### Source File

Copy source file into your project

## Communication

- Found a bug or have a feature request? [Open an issue](https://github.com/sgxiang/YTKKeyValueStore_Swift/issues).

- Want to contribute? [Submit a pull request](https://github.com/sgxiang/YTKKeyValueStore_Swift/pulls).

## Author

- [sgxiang](https://twitter.com/sgxiang1992)

