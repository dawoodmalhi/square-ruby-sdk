
# Upsert Booking Custom Attribute Response

Represents an [UpsertBookingCustomAttribute](../../doc/api/booking-custom-attributes.md#upsert-booking-custom-attribute) response.
Either `custom_attribute_definition` or `errors` is present in the response.

## Structure

`Upsert Booking Custom Attribute Response`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `custom_attribute` | [`Custom Attribute Hash`](../../doc/models/custom-attribute.md) | Optional | A custom attribute value. Each custom attribute value has a corresponding<br>`CustomAttributeDefinition` object. |
| `errors` | [`Array<Error Hash>`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. |

## Example (as JSON)

```json
{
  "custom_attribute": null,
  "errors": null
}
```
