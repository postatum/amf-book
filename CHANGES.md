# Changes in AMF 1.4.0

[Released Jun 08, 2018.](https://github.com/mulesoft/amf/releases/tag/v1.4.0)

This version has performance improvement's & bug fixing.
Just a little change of behaviour in generation & handlers.

## Generation

**Change behaviour of particular scalar strings**

When a scalar string text its from another type value, it will be quoted.

```
scalarvalue: "true"
```
instead of previous:
```
scalarvalue: true
```

## Handlers

Handlers were deprecated, use Promise/Future instead.

**Example:**

Use future:

{% codetabs name="Java", type="java" -%}
[example-raw](https://raw.githubusercontent.com/mulesoft/amf-examples/v1.3.1/src/main/java/co/acme/parse/Raml08Parsing.java#raml-08-parse-file-future)
{%- endcodetabs %}

Instead of using handler:

{% codetabs name="Java", type="java" -%}
[example-raw](https://raw.githubusercontent.com/mulesoft/amf-examples/v1.3.1/src/main/java/co/acme/parse/Raml08Parsing.java#raml-08-parse-file-handler)
{%- endcodetabs %}

Notice that the scalar is not a boolean, but a string. 

## Fixed issues

 - [APIMF-829 - java.lang.ClassCastException: amf.plugins.domain.shapes.models.NodeShape cannot be cast to amf.core.model.domain.templates.AbstractDeclaration](https://www.mulesoft.org/jira/browse/APIMF-829)
 - [APIMF-824 - AMF Validation fails with Scalar at / must have data type http://www.w3.org/2001/XMLSchema#string](https://www.mulesoft.org/jira/browse/APIMF-824)
 - [APIMF-820 - AMF validate fails with Error recursive shape](https://www.mulesoft.org/jira/browse/APIMF-820)
 - [APIMF-819 - StackOverflow validating an API](https://www.mulesoft.org/jira/browse/APIMF-819)
 - [APIMF-818 - Datetime datatype instantiated in json example does not validate](https://www.mulesoft.org/jira/browse/APIMF-818)
 - [APIMF-816 - AMF parser should consider methods connect and trace as valid](https://www.mulesoft.org/jira/browse/APIMF-816)
 - [APIMF-815 - Error validating required fields against JSON Schema](https://www.mulesoft.org/jira/browse/APIMF-815)
 - [APIMF-811 - API parsing takes too much time to run ReferenceResolutionStage step for validation resolution.](https://www.mulesoft.org/jira/browse/APIMF-811)
 - [APIMF-808 - YException: Not a YScalar](https://www.mulesoft.org/jira/browse/APIMF-808)
 - [APIMF-807 - AMF validation & resolution throws scala.MatchError: null](https://www.mulesoft.org/jira/browse/APIMF-807)
 - [APIMF-806 - NumberFormatException with date at parse time](https://www.mulesoft.org/jira/browse/APIMF-806)
 - [APIMF-804 - AMF resolution throws java.lang.Exception: Resolution error: Found shape without ID](https://www.mulesoft.org/jira/browse/APIMF-804)
 - [APIMF-801 - Discriminator is invalid for union types](https://www.mulesoft.org/jira/browse/APIMF-801)
 - [APIMF-799 - UnknownHostException while parsing an API](https://www.mulesoft.org/jira/browse/APIMF-799)
 - [APIMF-796 - Error "Not a YMap" when "responses" is empty](https://www.mulesoft.org/jira/browse/APIMF-796)
 - [APIMF-794 - AMF Validation fails with a property defined diferently in separate schemas](https://www.mulesoft.org/jira/browse/APIMF-794)
 - [APIMF-792 - org.yaml.model.YException: Not a YScalar](https://www.mulesoft.org/jira/browse/APIMF-792)
 - [APIMF-791 - Cannot parse data node from AST structure ?](https://www.mulesoft.org/jira/browse/APIMF-791)
 - [APIMF-790 - Scala match error: !include in Raml08DocumentParser](https://www.mulesoft.org/jira/browse/APIMF-790)
 - [APIMF-789 - NullPointerException in YamlParser.createNode()](https://www.mulesoft.org/jira/browse/APIMF-789)
 - [APIMF-788 - AMF Validate fails with min. cardinality 1 when using a pattern to declare a property name](https://www.mulesoft.org/jira/browse/APIMF-788)
 - [APIMF-787 - Schema is null for empty bodies](https://www.mulesoft.org/jira/browse/APIMF-787)
 - [APIMF-786 - OAS 2.0 an exception is thrown when body and formData parameters are linked at once](https://www.mulesoft.org/jira/browse/APIMF-786)
 - [APIMF-785 - OAS 2.0 Exception is thrown for in-formData parameter with no 'type' specified](https://www.mulesoft.org/jira/browse/APIMF-785)
 - [APIMF-783 - API resolution does not end](https://www.mulesoft.org/jira/browse/APIMF-783)
 - [APIMF-781 - AMF validation throws java.lang.Exception: Cannot find node with validation error](https://www.mulesoft.org/jira/browse/APIMF-781)
 - [APIMF-780 - AMF validation throws scala.MatchError](https://www.mulesoft.org/jira/browse/APIMF-780)
 - [APIMF-779 - AMF resolution throws InheritanceIncompatibleShapeError](https://www.mulesoft.org/jira/browse/APIMF-779)
 - [APIMF-778 - Unhandled status code 404](https://www.mulesoft.org/jira/browse/APIMF-778)
 - [APIMF-777 - AMF Validate throws NumberFormatException when using exclusiveMaximum in JSON Schema](https://www.mulesoft.org/jira/browse/APIMF-777)
 - [APIMF-776 - Validation ignores pattern on strings](https://www.mulesoft.org/jira/browse/APIMF-776)
 - [APIMF-774 - org.yaml.model.YException: Not a YSequence parsing an API](https://www.mulesoft.org/jira/browse/APIMF-774)
 - [APIMF-773 - No loader for urn:jsonschema:com:menasha:enterprise:Document](https://www.mulesoft.org/jira/browse/APIMF-773)
 - [APIMF-772 - AMF Throws NullPointerException while validating or resolving, TraitResolver.resolveOperation](https://www.mulesoft.org/jira/browse/APIMF-772)
 - [APIMF-770 - NullPointerException in org.yaml.model.YScalar](https://www.mulesoft.org/jira/browse/APIMF-770)
 - [APIMF-767 - RAML 1.0 empty default body results in Payload with no SourceAST and SourceNode](https://www.mulesoft.org/jira/browse/APIMF-767)
 - [APIMF-766 - AMF validation "hangs" validating RAML 1.0 API](https://www.mulesoft.org/jira/browse/APIMF-766)
 - [APIMF-764 - Validation of recursive type definition should fail (exception)](https://www.mulesoft.org/jira/browse/APIMF-764)
 - [APIMF-761 - Invalid version of "amf-shacl-node" in amf-client-js manifest](https://www.mulesoft.org/jira/browse/APIMF-761)
 - [APIMF-760 - Null defaultValue for query parameter in Raml 0.8](https://www.mulesoft.org/jira/browse/APIMF-760)
 - [APIMF-759 - Empty uri parameters for Raml 0.8](https://www.mulesoft.org/jira/browse/APIMF-759)
 - [APIMF-754 - scala match error in amf.plugins.domain.shapes.parser.XsdTypeDefMapping$.xsdFromString](https://www.mulesoft.org/jira/browse/APIMF-754)
 - [APIMF-753 - Error validating string when the value is either a number or a boolean wrapped into a string](https://www.mulesoft.org/jira/browse/APIMF-753)
 - [APIMF-752 - YException: Expecting !!str and !!map provided](https://www.mulesoft.org/jira/browse/APIMF-752)
 - [APIMF-750 - NoSuchElementException parsing JSON schema expression](https://www.mulesoft.org/jira/browse/APIMF-750)
 - [APIMF-749 - YException: Expecting !!str and !!int provided](https://www.mulesoft.org/jira/browse/APIMF-749)
 - [APIMF-748 - NullPointerException in RAML08 type parser](https://www.mulesoft.org/jira/browse/APIMF-748)
 - [APIMF-747 - AMF Validation took more than 10 minutes to validate](https://www.mulesoft.org/jira/browse/APIMF-747)
 - [APIMF-746 - Windows OS: error when trying to parse RAML file](https://www.mulesoft.org/jira/browse/APIMF-746)
 - [APIMF-744 - multipleOf facet validation not working with non-decimal values](https://www.mulesoft.org/jira/browse/APIMF-744)
 - [APIMF-743 - AMF Validation throws GC overhead with an api of Exchange](https://www.mulesoft.org/jira/browse/APIMF-743)
 - [APIMF-737 - AMF parsing fails with ClassCastException: org.yaml.model.YNonContent cannot be cast to org.yaml.model.YDocument](https://www.mulesoft.org/jira/browse/APIMF-737)
 - [APIMF-736 - RAML 1.0 Template parameters with no values cause serialization fall with exception](https://www.mulesoft.org/jira/browse/APIMF-736)
 - [APIMF-734 - Properties minimun and maximun not supported for numbers in raml 0.8](https://www.mulesoft.org/jira/browse/APIMF-734)
 - [APIMF-732 - JsonSchema generated for Payload in Raml 0.8 always turn on additionalProperties](https://www.mulesoft.org/jira/browse/APIMF-732)
 - [APIMF-731 - JsonSchema for Arrays in  RAML 1.0 doesn't specified type](https://www.mulesoft.org/jira/browse/APIMF-731)
 - [APIMF-730 - AMF Validates invalid datetime example](https://www.mulesoft.org/jira/browse/APIMF-730)
 - [APIMF-729 - RAML 1.0 and OAS 2.0. YAML. In examples "true" and "false" strings are serialized as booleans.](https://www.mulesoft.org/jira/browse/APIMF-729)
 - [APIMF-727 - Error getting a jsonSchema from a queryParams of type File in RAML 0.8](https://www.mulesoft.org/jira/browse/APIMF-727)
 - [APIMF-725 - EndPoint Uri Parameters order is unpredictable](https://www.mulesoft.org/jira/browse/APIMF-725)
 - [APIMF-723 - Resource loader that sets invalid URI to Content ends with exception in validation](https://www.mulesoft.org/jira/browse/APIMF-723)
 - [APIMF-722 - FileShape bug in RAML dump](https://www.mulesoft.org/jira/browse/APIMF-722)
 - [APIMF-720 - Inconsistency found when defining request media types in raml and oas](https://www.mulesoft.org/jira/browse/APIMF-720)
 - [APIMF-719 - multipart/form-data media types are handled differently for oas and raml](https://www.mulesoft.org/jira/browse/APIMF-719)
 - [APIMF-718 - Add withSchema method to Parameter](https://www.mulesoft.org/jira/browse/APIMF-718)

# Changes in AMF 1.3.5

[Released May 09, 2018.](https://github.com/mulesoft/amf/releases/tag/v1.3.5)

## Vocabularies Plugin

**Change header in Dialect definition file**

```
#%Dialect 1.0
```
instead of previous:
```
#%RAML 1.0 Dialect
```

**Change header in Vocabularies definition file**

```
#%Vocabulary 1.0
```
instead of previous:
```
#%RAML 1.0 Vocabulary
```

## Domain Element

All the graphs method inside a DomainElement are now inside a Graph Object that is obtained with "graph" method in the DomainElement

# Changes in AMF 1.3.1

[Released April 13, 2018.](https://github.com/mulesoft/amf/releases/tag/v1.3.1)

AMF 1.3.1 does not introduce any non-backwards-compatible change.

## Custom Resolution

A resolution pipeline can be optionally specified to run a different set of steps. See [Resolution](programming/resolution.md).

## Fields

Scalar value annotations are now typed and accessible.

Option method is now Java `Optional` and JS `UndefOr`.

See [Model](programming/model.md#fields).

## Dialects

Added support for parsing dialects/instances from JSON files through the use of `$dialect`.

Example of dialect definition:

```json
{
  "$dialect": "RAML 1.0 Dialect",
  "dialect": "TestInstance",
  "version": "1.17",
  "nodeMappings": {
    "RootNode": {
      "classTerm": "tmp.str",
      "mapping": {
        "str": {
          "propertyTerm": "tmp.str",
          "range": "string"
        }
      }
    }
  },
  "documents": {
    "root": {
      "encodes": "RootNode"
    }
  },
  "external": {
    "tmp": "http://test/com/tmp#"
  }
}
```

Dialect instance for the above example:

```json
{
  "$dialect": "TestInstance 1.17",
  "str": "hey ho, let's go"
}
```

## Fixed issues and stories

[APIMF-453](https://www.mulesoft.org/jira/browse/APIMF-453)
[APIMF-489](https://www.mulesoft.org/jira/browse/APIMF-489)
[APIMF-490](https://www.mulesoft.org/jira/browse/APIMF-490)
[APIMF-493](https://www.mulesoft.org/jira/browse/APIMF-493)
[APIMF-494](https://www.mulesoft.org/jira/browse/APIMF-494)
[APIMF-496](https://www.mulesoft.org/jira/browse/APIMF-496)
[APIMF-497](https://www.mulesoft.org/jira/browse/APIMF-497)
[APIMF-498](https://www.mulesoft.org/jira/browse/APIMF-498)
[APIMF-499](https://www.mulesoft.org/jira/browse/APIMF-499)
[APIMF-500](https://www.mulesoft.org/jira/browse/APIMF-500)
[APIMF-540](https://www.mulesoft.org/jira/browse/APIMF-540)
[APIMF-541](https://www.mulesoft.org/jira/browse/APIMF-541)
[APIMF-545](https://www.mulesoft.org/jira/browse/APIMF-545)
[APIMF-546](https://www.mulesoft.org/jira/browse/APIMF-546)
[APIMF-546](https://www.mulesoft.org/jira/browse/APIMF-546)
[APIMF-548](https://www.mulesoft.org/jira/browse/APIMF-548)
[APIMF-552](https://www.mulesoft.org/jira/browse/APIMF-552)
[APIMF-553](https://www.mulesoft.org/jira/browse/APIMF-553)
[APIMF-556](https://www.mulesoft.org/jira/browse/APIMF-556)
[APIMF-564](https://www.mulesoft.org/jira/browse/APIMF-564)
[APIMF-566](https://www.mulesoft.org/jira/browse/APIMF-566)
[APIMF-568](https://www.mulesoft.org/jira/browse/APIMF-568)
[APIMF-570](https://www.mulesoft.org/jira/browse/APIMF-570)
[APIMF-571](https://www.mulesoft.org/jira/browse/APIMF-571)
[APIMF-572](https://www.mulesoft.org/jira/browse/APIMF-572)
[APIMF-573](https://www.mulesoft.org/jira/browse/APIMF-573)
[APIMF-574](https://www.mulesoft.org/jira/browse/APIMF-574)
[APIMF-576](https://www.mulesoft.org/jira/browse/APIMF-576)
[APIMF-577](https://www.mulesoft.org/jira/browse/APIMF-577)
[APIMF-578](https://www.mulesoft.org/jira/browse/APIMF-578)
[APIMF-579](https://www.mulesoft.org/jira/browse/APIMF-579)
[APIMF-580](https://www.mulesoft.org/jira/browse/APIMF-580)
[APIMF-581](https://www.mulesoft.org/jira/browse/APIMF-581)
[APIMF-582](https://www.mulesoft.org/jira/browse/APIMF-582)
[APIMF-587](https://www.mulesoft.org/jira/browse/APIMF-587)
[APIMF-595](https://www.mulesoft.org/jira/browse/APIMF-595)
[APIMF-612](https://www.mulesoft.org/jira/browse/APIMF-612)
[APIMF-615](https://www.mulesoft.org/jira/browse/APIMF-615)
[APIMF-620](https://www.mulesoft.org/jira/browse/APIMF-620)
[APIMF-626](https://www.mulesoft.org/jira/browse/APIMF-626)
[APIMF-626](https://www.mulesoft.org/jira/browse/APIMF-626)
[APIMF-627](https://www.mulesoft.org/jira/browse/APIMF-627)
[APIMF-628](https://www.mulesoft.org/jira/browse/APIMF-628)
[APIMF-631](https://www.mulesoft.org/jira/browse/APIMF-631)
[APIMF-632](https://www.mulesoft.org/jira/browse/APIMF-632)
[APIMF-634](https://www.mulesoft.org/jira/browse/APIMF-634)
[APIMF-635](https://www.mulesoft.org/jira/browse/APIMF-635)
[APIMF-636](https://www.mulesoft.org/jira/browse/APIMF-636)
[APIMF-639](https://www.mulesoft.org/jira/browse/APIMF-639)
[APIMF-640](https://www.mulesoft.org/jira/browse/APIMF-640)
[APIMF-641](https://www.mulesoft.org/jira/browse/APIMF-641)
[APIMF-642](https://www.mulesoft.org/jira/browse/APIMF-642)
[APIMF-645](https://www.mulesoft.org/jira/browse/APIMF-645)
[APIMF-651](https://www.mulesoft.org/jira/browse/APIMF-651)
[APIMF-652](https://www.mulesoft.org/jira/browse/APIMF-652)
[APIMF-656](https://www.mulesoft.org/jira/browse/APIMF-656)
[APIMF-665](https://www.mulesoft.org/jira/browse/APIMF-665)
[APIMF-666](https://www.mulesoft.org/jira/browse/APIMF-666)

# Changes in AMF 1.3.0

[Released March 27, 2018.](https://github.com/mulesoft/amf/releases/tag/v1.3.0)

AMF 1.3.0 introduces non-backwards-compatible changes

## Packages and naming

Client classes are moving to ```amf.client.*``` package. All core, webapi, and vocabularies client classes are moved. Plugins, parsers, renderers, and other classes where moved as well.

All ```*Generator``` classes are now ```*Renderer```.

## Fields

Fields on client classes (```String```, ```Int```, etc.) are now ```StrField```, ```IntField```, etc. This allows to retrieve raml scalar-value annotations, lexical information, etc. for all scalar values. As well, some convenient methods where added to handle with ```undefined``` or ```null``` field values:

```
val field: StrField | Intfield | BoolField | FloatField | DoubleField = ...

field.value() // returns the actual value of this field. If field is null will return "", 0, or false depending on the field type.
field.nonNull // returns a boolean indicating the field is not null
field.isNull // returns a boolean indicating the field is null or undefined
field.option() // returns an optional value for this field
field.is("Some value") // returns true if field value is not-null and equals given value
field.is(_ == "Some value") // returns true if field value is not-null and accepts given predicate

/** Only for StrField */
field.isNullOrEmpty // returns a boolean indicating the field is null, undefined, or an empty string
field.nonEmpty // returns a boolean indicating the field is not null, and string value is not empty
```

## Vocabularies Plugin

Vocabularies plugin has been rewritten from scratch.

**Changes in Dialect definition file**
```
documents:
  library:
    declares:
      products: ProductNode
  root:
    encodes: PresentationNode
```
instead of previous:
```
raml:
  module:
    declares:
      products: ProductNode
  document:
    encodes: PresentationNode
```

- replace ```hash``` for ```mapKey```
- If you use ```mapKey```, is no longer necessary to specify ```allowMultiple: true```
- range ```number``` to ```integer```

**Changes in Vocabulary definition file**
- range ```number``` to ```integer```

## WebApi Plugin

WebApi model has changed for future OAS 3.X support. Almost all changes where additions:

**WebApi**
- **servers** array field was added
- **baseUriparameters** field was deleted (it's now *default server* variables field)
- **host** field was deleted (it's now part of the *default server* url field)
- **basePath** field was deleted (it's now part of the *default server* url field)

**Server**
- **url** field was added
- **description** field was added
- **variables** field was added

A *default server* is synthesized when parsing RAML or OAS 2.

**EndPoint**
- **summary** field was added
- **servers** array field was added

**Operation**
- **callbacks** field was added
- **servers** array field was added

**Callback**
- **name** field was added
- **expression** field was added
- **endpoint** field was added

**Parameter**
- **deprecated** field was added
- **allowEmptyValue** field was added
- **style** field was added
- **explode** field was added
- **allowReserved** field was added
- **payloads** field was added
- **examples** field was added

**Payload**
- **examples** field was added
- **encoding** field was added

**Encoding**
- **propertyName** field was added
- **contentType** field was added
- **headers** array field was added
- **style** field was added
- **explode** field was added
- **allowReserved** field was added

**Request**
- **description** field was added
- **required** field was added
- **cookieParameters** array field was added

**Response**
- **links** field was added

**TemplatedLink**
- **name** field was added
- **description** field was added
- **template** field was added
- **operationId** field was added
- **mapping** array field was added
- **requestBody** field was added
- **server** field was added

**IriTemplateMapping**
- **templateVariable** field was added
- **linkExpression** field was added

**SecurityScheme**
- **withHttpSettings** setting was added
- **withOpenIdConnectSettings** setting was added

**HttpSettings**
- **scheme** field was added
- **bearerFormat** field was added

**OpenIdconnect**
- **url** field was added

## Other changes

- ```resolve``` method now accepts a pipelineId to customize a resolution pipeline.
- ```generateString``` method from ```Renderer``` is now async.

# Changes in AMF 1.2.1

[Released March 19, 2018.](https://github.com/mulesoft/amf/releases/tag/v1.2.1)

AMF 1.2.1 does not introduce any non-backwards-compatible change.

## Examples

Example had a ```value``` field containing the literal string parsed example.
A ```structuredValue``` field was added, containing the parsed example as a ```DataNode```.

## JsonSchema generation

All ```AnyShape``` instances now contains a handy ```toJsonSchema``` method that returns the json schema for the underlying shape.

As well a ```validate(payload)``` method was added to all ```AnyShape``` instances.
