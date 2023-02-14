# SimpleXMLWriter
SimpleXMLWriter is one C++ File header which uses operators to build xml.

## Usage
```cpp
 CXMLWriter m_XMLWriter;

CXMLWriterNode& m_XMLNode = m_XMLWriter["xml"];
m_XMLNode["Key0"]("Index", "0")("Size", "test");
m_XMLNode["Key1"]("Index", "1")("Size", "test");
m_XMLNode["Key2"]("Index", "2")("Size", "test");

m_XMLNode["Key0"]["AnotherKey"] = "Value0";
m_XMLNode["Key1"]["AnotherKey"] = "Value1";
m_XMLNode["Key2"]["AnotherKey"] = "Value2";

m_XMLNode["Key0"]["AnotherKey"]["Another"]("Attribute0", "Value0") = "Test0";
m_XMLNode["Key1"]["AnotherKey"]["Another"]("Attribute0", "Value0") = "Test1";
```

## Output from usage
```xml
<?xml version="1.0" encoding="UTF-8"?>
<xml>
	<Key0 Index="0" Size="test">
		<AnotherKey>
			Value0
			<Another Attribute0="Value0">Test0</Another>
		</AnotherKey>
	</Key0>
	<Key1 Index="1" Size="test">
		<AnotherKey>
			Value1
			<Another Attribute0="Value0">Test1</Another>
		</AnotherKey>
	</Key1>
	<Key2 Index="2" Size="test">
		<AnotherKey>Value2</AnotherKey>
	</Key2>
</xml>

```
