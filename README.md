# XMLLib

<img width="100" alt="img" src="https://rawgit.com/stylekit/img/master/XMLLib.svg">

- Makes parsing and modifying xml data easier (CRUD)
- Supports parsing and modifying at deep indices 

```swift
/*Simple example:*/
let xml = "<a><one>text</one></a>".xml
let child = xml.firstNode("one")!
Swift.print(child.value)//Output: text
/*Advance examples:*/
XMLParser.childAt(xml,[0,2,1])//Output: the second item in the third item in root
XMLModifier.setAttributeAt(xml,[0,1],["color":"blue","gradient":"teal"])//Sets the color and gradient attributes in the second item in root
/*Creating xml:*/
let xml = "<data></data>".xml
xml.appendChild("<files></files>".xml)
let file = "<file></file>".xml
file["date"] = "2022-10-02"
file.stringValue = "/Desktop/temp.jpg"
xml.firstNode("files").appendChild(file)
print(xml.XMLString)//Output: "<data><files><file date=\"2022-10-02\">/Desktop/temp.jpg</file></files></data>"
```
