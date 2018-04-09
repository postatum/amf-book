# Changes in AMF snapshot

AMF snapshot does not introduce any non-backwards-compatible change.

## Custom Resolution

A resolution pipeline can be optionally specified to run a different set of steps. See [Resolution](programming/resolution.md).

## Fields

Scalar value annotations are now typed and accessible.

Option method is now Java `Optional` and JS `UndefOr`.

See [Model](programming/model.md#fields).

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
