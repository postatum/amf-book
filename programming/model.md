# Object Oriented Model

AMF provides an object oriented model to build, modify, and traverse through units and elements. Each plugin exposes different classes matching specific domains.

##Fields

Fields on classes are usually wrapped with a convenient class to avoid the use of `null / undefined`. These field wrappers are defined on package ```amf.client.model```.

Available field wrappers are `StrField`, `IntField`, `BoolField`, `DoubleField`, `FloatField`, and `AnyField`.

###Accessing defined field

{% codetabs name="Java", type="java" -%}
[example-raw](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/test/java/co/acme/model/Fields.java#field-defined)
{%- endcodetabs %}

###Accessing `null / undefined` field

{% codetabs name="Java", type="java" -%}
[example-raw](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/test/java/co/acme/model/Fields.java#field-undefined)
{%- endcodetabs %}

###Accessing scalar annotations

To access custom annotations, see `annotations > custom` field method:

{% codetabs name="Java", type="java" -%}
[example-raw](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/test/java/co/acme/model/Fields.java#field-annotations)
{%- endcodetabs %}

Above example corresponds to the following webapi definition:

{% codetabs name="Java", type="java" -%}
[example-raml](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/main/resources/examples/scalar-annotations.raml)
{%- endcodetabs %}

## WebApi plugin

AMF WebApi plugin allows to programmatically create and traverse a WebApi.

{% codetabs name="Java", type="java" -%}
[example-raw](https://raw.githubusercontent.com/mulesoft/amf-examples/snapshot/src/test/java/co/acme/model/WebApiBuilder.java#raml-10-webapi-builder)
{%- endcodetabs %}

## Fields