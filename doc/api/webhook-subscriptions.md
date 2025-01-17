# Webhook Subscriptions

```ruby
webhook_subscriptions_api = client.webhook_subscriptions
```

## Class Name

`WebhookSubscriptionsApi`

## Methods

* [List Webhook Event Types](../../doc/api/webhook-subscriptions.md#list-webhook-event-types)
* [List Webhook Subscriptions](../../doc/api/webhook-subscriptions.md#list-webhook-subscriptions)
* [Create Webhook Subscription](../../doc/api/webhook-subscriptions.md#create-webhook-subscription)
* [Delete Webhook Subscription](../../doc/api/webhook-subscriptions.md#delete-webhook-subscription)
* [Retrieve Webhook Subscription](../../doc/api/webhook-subscriptions.md#retrieve-webhook-subscription)
* [Update Webhook Subscription](../../doc/api/webhook-subscriptions.md#update-webhook-subscription)
* [Update Webhook Subscription Signature Key](../../doc/api/webhook-subscriptions.md#update-webhook-subscription-signature-key)
* [Test Webhook Subscription](../../doc/api/webhook-subscriptions.md#test-webhook-subscription)


# List Webhook Event Types

Lists all webhook event types that can be subscribed to.

```ruby
def list_webhook_event_types(api_version: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `api_version` | `String` | Query, Optional | The API version for which to list event types. Setting this field overrides the default version used by the application. |

## Response Type

[`List Webhook Event Types Response Hash`](../../doc/models/list-webhook-event-types-response.md)

## Example Usage

```ruby
result = webhook_subscriptions_api.list_webhook_event_types()

if result.success?
  puts result.data
elsif result.error?
  warn result.errors
end
```


# List Webhook Subscriptions

Lists all webhook subscriptions owned by your application.

```ruby
def list_webhook_subscriptions(cursor: nil,
                               include_disabled: false,
                               sort_order: nil,
                               limit: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `String` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for your original query.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). |
| `include_disabled` | `TrueClass\|FalseClass` | Query, Optional | Includes disabled [Subscription](../../doc/models/webhook-subscription.md)s.<br>By default, all enabled [Subscription](../../doc/models/webhook-subscription.md)s are returned.<br>**Default**: `false` |
| `sort_order` | [`String (Sort Order)`](../../doc/models/sort-order.md) | Query, Optional | Sorts the returned list by when the [Subscription](../../doc/models/webhook-subscription.md) was created with the specified order.<br>This field defaults to ASC. |
| `limit` | `Integer` | Query, Optional | The maximum number of results to be returned in a single page.<br>It is possible to receive fewer results than the specified limit on a given page.<br>The default value of 100 is also the maximum allowed value.<br><br>Default: 100 |

## Response Type

[`List Webhook Subscriptions Response Hash`](../../doc/models/list-webhook-subscriptions-response.md)

## Example Usage

```ruby
include_disabled = false

result = webhook_subscriptions_api.list_webhook_subscriptions(include_disabled: include_disabled, )

if result.success?
  puts result.data
elsif result.error?
  warn result.errors
end
```


# Create Webhook Subscription

Creates a webhook subscription.

```ruby
def create_webhook_subscription(body:)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Create Webhook Subscription Request Hash`](../../doc/models/create-webhook-subscription-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

[`Create Webhook Subscription Response Hash`](../../doc/models/create-webhook-subscription-response.md)

## Example Usage

```ruby
body = {}
body[:idempotency_key] = '63f84c6c-2200-4c99-846c-2670a1311fbf'
body[:subscription] = {}
body[:subscription][:name] = 'Example Webhook Subscription'
body[:subscription][:event_types] = ['payment.created', 'payment.updated']
body[:subscription][:notification_url] = 'https://example-webhook-url.com'
body[:subscription][:api_version] = '2021-12-15'

result = webhook_subscriptions_api.create_webhook_subscription(body: body)

if result.success?
  puts result.data
elsif result.error?
  warn result.errors
end
```


# Delete Webhook Subscription

Deletes a webhook subscription.

```ruby
def delete_webhook_subscription(subscription_id:)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscription_id` | `String` | Template, Required | [REQUIRED] The ID of the [Subscription](../../doc/models/webhook-subscription.md) to delete. |

## Response Type

[`Delete Webhook Subscription Response Hash`](../../doc/models/delete-webhook-subscription-response.md)

## Example Usage

```ruby
subscription_id = 'subscription_id0'

result = webhook_subscriptions_api.delete_webhook_subscription(subscription_id: subscription_id)

if result.success?
  puts result.data
elsif result.error?
  warn result.errors
end
```


# Retrieve Webhook Subscription

Retrieves a webhook subscription identified by its ID.

```ruby
def retrieve_webhook_subscription(subscription_id:)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscription_id` | `String` | Template, Required | [REQUIRED] The ID of the [Subscription](../../doc/models/webhook-subscription.md) to retrieve. |

## Response Type

[`Retrieve Webhook Subscription Response Hash`](../../doc/models/retrieve-webhook-subscription-response.md)

## Example Usage

```ruby
subscription_id = 'subscription_id0'

result = webhook_subscriptions_api.retrieve_webhook_subscription(subscription_id: subscription_id)

if result.success?
  puts result.data
elsif result.error?
  warn result.errors
end
```


# Update Webhook Subscription

Updates a webhook subscription.

```ruby
def update_webhook_subscription(subscription_id:,
                                body:)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscription_id` | `String` | Template, Required | [REQUIRED] The ID of the [Subscription](../../doc/models/webhook-subscription.md) to update. |
| `body` | [`Update Webhook Subscription Request Hash`](../../doc/models/update-webhook-subscription-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

[`Update Webhook Subscription Response Hash`](../../doc/models/update-webhook-subscription-response.md)

## Example Usage

```ruby
subscription_id = 'subscription_id0'
body = {}
body[:subscription] = {}
body[:subscription][:name] = 'Updated Example Webhook Subscription'
body[:subscription][:enabled] = false

result = webhook_subscriptions_api.update_webhook_subscription(subscription_id: subscription_id, body: body)

if result.success?
  puts result.data
elsif result.error?
  warn result.errors
end
```


# Update Webhook Subscription Signature Key

Updates a webhook subscription by replacing the existing signature key with a new one.

```ruby
def update_webhook_subscription_signature_key(subscription_id:,
                                              body:)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscription_id` | `String` | Template, Required | [REQUIRED] The ID of the [Subscription](../../doc/models/webhook-subscription.md) to update. |
| `body` | [`Update Webhook Subscription Signature Key Request Hash`](../../doc/models/update-webhook-subscription-signature-key-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

[`Update Webhook Subscription Signature Key Response Hash`](../../doc/models/update-webhook-subscription-signature-key-response.md)

## Example Usage

```ruby
subscription_id = 'subscription_id0'
body = {}
body[:idempotency_key] = 'ed80ae6b-0654-473b-bbab-a39aee89a60d'

result = webhook_subscriptions_api.update_webhook_subscription_signature_key(subscription_id: subscription_id, body: body)

if result.success?
  puts result.data
elsif result.error?
  warn result.errors
end
```


# Test Webhook Subscription

Tests a webhook subscription by sending a test event to the notification URL.

```ruby
def test_webhook_subscription(subscription_id:,
                              body:)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `subscription_id` | `String` | Template, Required | [REQUIRED] The ID of the [Subscription](../../doc/models/webhook-subscription.md) to test. |
| `body` | [`Test Webhook Subscription Request Hash`](../../doc/models/test-webhook-subscription-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Response Type

[`Test Webhook Subscription Response Hash`](../../doc/models/test-webhook-subscription-response.md)

## Example Usage

```ruby
subscription_id = 'subscription_id0'
body = {}
body[:event_type] = 'payment.created'

result = webhook_subscriptions_api.test_webhook_subscription(subscription_id: subscription_id, body: body)

if result.success?
  puts result.data
elsif result.error?
  warn result.errors
end
```

