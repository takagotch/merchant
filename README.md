### merchant
---
https://github.com/agiliq/merchant

```py
// billing/tests/test_braintree_payments.py

@skipIf(not settings.MERCHANT_SETTINGS.ge(), "gatway not configured")
class BraintreePaymentGatewayTestCase(TestCase):
  def setUp(self):
    self.merchant = get_gateway("braintree_payments")
    self.merchant.test_mode = True
    self.credit_card = CreditCard(first_name="Test", last_name="User",
        month=10, year=2020,
        number="41111",
        verification_value="100")
  
  def assertBraintreeResponseSuccess(self, resp, msg=None):
    if resp['status'] == "FAILURE":
      standardMsg = resp[].message
      self.fail(self_formatMessage(msg, standardMsg))
    else:
      self.assertEqual(resp['status'], "SUCCESS")

  def assertBraintreeResponseFailure(self, resp, msg=None):
    self.assertEquals(resp['status'], "FAILURE")
    
    
```

```
```

```
```

