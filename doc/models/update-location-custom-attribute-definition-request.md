
# Update Location Custom Attribute Definition Request

Represents an [UpdateLocationCustomAttributeDefinition](../../doc/api/location-custom-attributes.md#update-location-custom-attribute-definition) request.

## Structure

`Update Location Custom Attribute Definition Request`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `custom_attribute_definition` | [`Custom Attribute Definition Hash`](../../doc/models/custom-attribute-definition.md) | Required | Represents a definition for custom attribute values. A custom attribute definition<br>specifies the key, visibility, schema, and other properties for a custom attribute. |
| `idempotency_key` | `String` | Optional | A unique identifier for this request, used to ensure idempotency. For more information,<br>see [Idempotency](https://developer.squareup.com/docs/build-basics/common-api-patterns/idempotency).<br>**Constraints**: *Maximum Length*: `45` |

## Example (as JSON)

```json
{
  "custom_attribute_definition": {
    "description": "Update the description as desired.",
    "visibility": "VISIBILITY_READ_ONLY"
  }
}
```

