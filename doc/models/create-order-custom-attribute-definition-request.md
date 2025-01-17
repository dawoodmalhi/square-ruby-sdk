
# Create Order Custom Attribute Definition Request

Represents a create request for an order custom attribute definition.

## Structure

`Create Order Custom Attribute Definition Request`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `custom_attribute_definition` | [`Custom Attribute Definition Hash`](../../doc/models/custom-attribute-definition.md) | Required | Represents a definition for custom attribute values. A custom attribute definition<br>specifies the key, visibility, schema, and other properties for a custom attribute. |
| `idempotency_key` | `String` | Optional | A unique identifier for this request, used to ensure idempotency.<br>For more information, see [Idempotency](https://developer.squareup.com/docs/basics/api101/idempotency).<br>**Constraints**: *Maximum Length*: `45` |

## Example (as JSON)

```json
{
  "custom_attribute_definition": {
    "description": "The number of people seated at a table",
    "key": "cover-count",
    "name": "Cover count",
    "schema": null,
    "visibility": "VISIBILITY_READ_WRITE_VALUES"
  },
  "idempotency_key": "IDEMPOTENCY_KEY"
}
```

