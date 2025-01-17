
# Create Dispute Evidence File Response

Defines the fields in a `CreateDisputeEvidenceFile` response.

## Structure

`Create Dispute Evidence File Response`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `errors` | [`Array<Error Hash>`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. |
| `evidence` | [`Dispute Evidence Hash`](../../doc/models/dispute-evidence.md) | Optional | - |

## Example (as JSON)

```json
{
  "evidence": {
    "dispute_id": "bVTprrwk0gygTLZ96VX1oB",
    "evidence_file": {
      "filename": "customer-interaction.jpg",
      "filetype": "image/jpeg"
    },
    "id": "TOomLInj6iWmP3N8qfCXrB",
    "uploaded_at": "2022-05-18T16:01:10.000Z"
  }
}
```

