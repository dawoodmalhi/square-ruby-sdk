
# Loyalty Event Other

Provides metadata when the event `type` is `OTHER`.

## Structure

`Loyalty Event Other`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `loyalty_program_id` | `String` | Required | The Square-assigned ID of the [loyalty program](../../doc/models/loyalty-program.md).<br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` |
| `points` | `Integer` | Required | The number of points added or removed. |

## Example (as JSON)

```json
{
  "points": 236
}
```

