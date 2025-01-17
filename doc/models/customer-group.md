
# Customer Group

Represents a group of customer profiles.

Customer groups can be created, be modified, and have their membership defined using
the Customers API or within the Customer Directory in the Square Seller Dashboard or Point of Sale.

## Structure

`Customer Group`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Optional | A unique Square-generated ID for the customer group.<br>**Constraints**: *Maximum Length*: `255` |
| `name` | `String` | Required | The name of the customer group. |
| `created_at` | `String` | Optional | The timestamp when the customer group was created, in RFC 3339 format. |
| `updated_at` | `String` | Optional | The timestamp when the customer group was last updated, in RFC 3339 format. |

## Example (as JSON)

```json
{
  "name": "name0"
}
```

