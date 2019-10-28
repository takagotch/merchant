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
  
  def assertCardSupported(self):
    self.credict_card.number = "0000"
    self.assertRaises(CardNotSupported,
        lambda: self.merchant.purchase(1000, self.credit_card))
  
  
  
  def testRecurring3(self):
    options = {
      "": {},
      "": {},
    }
    resp = self.merchant.recurring(20, self.credit_card, option=options)
    self.assertBraintreeResponseSuccess(resp)
    subscription = resp["response"].subscription
    self.assertEqual(subscription.number_of_billing_cycles, 12)
```

```
```

```
```

