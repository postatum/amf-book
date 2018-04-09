# Object Oriented Model

AMF provides an object oriented model to build, modify, and traverse through units and elements. Each plugin exposes different classes matching specific domains.

##Fields

Fields on classes are usually wrapped with a convenient class to avoid the use of `null / undefined`. These field wrappers are defined on package ```amf.client.model```.

Available field wrappers are `StrField`, `IntField`, `BoolField`, `DoubleField`, `FloatField`, and `AnyField`.

###Accessing defined field

[example-java](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/test/java/co/acme/model/Fields.java#field-defined)

###Accessing `null / undefined` field

[example-java](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/test/java/co/acme/model/Fields.java#field-undefined)

###Accessing scalar annotations

To access custom annotations, see `annotations > custom` field method:

[example-java](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/test/java/co/acme/model/Fields.java#field-annotations)

Above example corresponds to the following webapi definition:

[example-raml](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/main/resources/examples/scalar-annotations.raml)

## WebApi plugin

AMF WebApi plugin allows to programmatically create and traverse a WebApi.

[example-java](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/test/java/co/acme/model/WebApiBuilder.java#raml-10-webapi-builder)

## Fields