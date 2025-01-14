# PeakPoint Packages

This endpoint allows for batch creation of multiple packages in DynamoDB.

## Endpoint

```
POST /api/items
```

## Request Body

```json
{
  "items": [
    {
      "booking_code": "string",
      "main_passenger_name": "string",
      "number_of_nights": "string",
      "start_date": "string",
      "end_date": "string",
      "supplier_name": "string",
      "description": "string",
      "zone_level_1": "string",
      "date_of_confirmation": "string",
      "status": "string",
      "agent_name": "string",
      "agent_remark": "string",
      "problem": "string",
      "extra_remark_1": "string",
      "extra_remark_2": "string"
    }
  ]
}
```

## Responses

### Success Response

**Code**: 200 OK

```json
{
  "message": "Items added successfully",
  "unprocessedItems": {}
}
```

### Error Responses

**Code**: 400 BAD REQUEST

```json
{
  "message": "Items must be a non-empty array."
}
```

**Code**: 500 INTERNAL SERVER ERROR

```json
{
  "message": "Error adding items.",
  "error": "error message"
}
```

or

```json
{
  "message": "Table name is not configured in the server."
}
```

## Notes

- Timestamps and id are automatically added
