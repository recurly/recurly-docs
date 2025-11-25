---
title: 'Free Trial Gateway Routing Continuity '
deprecated: false
hidden: true
metadata:
  robots: index
---
In order for the routing to occur as the merchant is expecting for both the verification on the free trial and continuously on the subscription using the v3/subscriptions endpoint they will need to place gateway_code in the subscriptions call body twice.  
Once at the top-level subscription (which is what they are not currently doing and controls the renewal behavior) 
and again at the billing info level (currently in their request which is controlling the verification behavior).

```json
{
  "currency":"USD",
  "plan_code":"example_plan_1",
	"account":{
    "code":"new_account_1",
		"billing_info":{
			"token_id":"rjs-token",
			"gateway_code":"your-gateway-code"
			}
		},
	"gateway_code":"your-gateway-code"
}
```

<br />
