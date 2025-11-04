---
title: API transaction errors
excerpt: >-
  A reference for understanding and handling transaction errors returned by
  Recurly when gateway declines occur, complete with example XML and JSON error
  payloads.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

When a payment attempt is declined by your gateway, Recurly translates the gateway’s error code into a structured error response—complete with a machine‑readable `error_code`, a human‑friendly `customer_message`, and the original `gateway_error_code`. You’ll encounter these errors any time you create subscriptions, update billing info, or process one‑time transactions.

Transaction errors represent failures during payment processing. Each error includes:

* `error_code`: a Recurly‑specific code indicating the failure reason.
* `error_category`: classification such as `fraud` or `validation`.
* `merchant_message`: guidance for your logs or support team.
* `customer_message`: a user‑facing explanation to display in your UI.
* `gateway_error_code`: the raw code returned by your payment gateway.

# Reference

## Approved

| Code                    | Customer Message | Merchant Message                                            |
| ----------------------- | ---------------- | ----------------------------------------------------------- |
| `approved`              | Approved         | Approved                                                    |
| `approved_fraud_review` | Approved         | Approved, flagged for fraud review in your payment gateway. |

## Soft

| Code                                      | Customer Message                                                                                                                                         | Merchant Message                                                                                                                                            |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `declined`                                | Your transaction was declined. Please use a different card or contact your bank.                                                                         | The customer's bank has declined their card. The customer will need to contact their bank to learn the cause.                                               |
| `declined_saveable`                       | The transaction was declined. Please use a different card or contact your bank.                                                                          | The transaction was declined without specific information.  Please contact your payment gateway for more details or ask the customer to contact their bank. |
| `insufficient_funds`                      | Your transaction was declined due to insufficient funds in your account. Please use a different card or contact your bank.                               | The card has insufficient funds to cover the cost of the transaction.                                                                                       |
| `temporary_hold`                          | Your card has a temporary hold. Please use a different card or contact your bank.                                                                        | The issuing bank has a temporary hold on the card. This is known as a 'Do Not Honor' response.                                                              |
| `try_again`                               | The transaction was declined. Please use a different card or contact your bank.                                                                          | The card was declined with the response to try again later.                                                                                                 |
| `too_many_attempts`                       | The transaction was declined. You have exceeded a reasonable number of attempts. Please wait a while before retrying your card, or try a different card. | The transaction was declined because of too many authorization attempts.                                                                                    |
| `simultaneous`                            | The transaction was declined because a simultaneous transaction is already in progress for your account. Please wait 10 seconds before trying again.     | The transaction was declined because a simultaneous transaction was already in progress for the account.                                                    |
| `partial_approval`                        | The transaction was declined due to insufficient funds in your account. Please use a different card or contact your bank.                                | The transaction was only approved for a partial amount of the transaction. This occurs with gift cards.                                                     |
| `call_issuer`                             | Your transaction was declined. Please contact your bank for further details or try another card.                                                         | The transaction was declined by the payment gateway. Contact the card issuer for more details.                                                              |
| `call_issuer_update_cardholder_data`      | Your transaction was declined. Please contact your bank for further details or try another card.                                                         | The transaction was declined by the payment gateway. Contact the card issuer for more details.                                                              |
| `processor_not_available`                 | Please contact support: the payment system experienced an unspecified error with your card issuer.                                                       | The payment processor was unavailable for the transaction. Contact your payment gateway for more details.                                                   |
| `cancelled`                               | This payment was cancelled at your request.                                                                                                              | This payment was cancelled at your request.                                                                                                                 |
| `paypal_primary_declined`                 | Your primary funding source was declined. Please try again to use your secondary funding source.                                                         | The primary funding source failed but the transaction can be attempted again. The next attempt will use the alternate funding source.                       |
| `paypal_declined_use_alternate`           | Your PayPal funding source was declined. Please try again to use an alternate funding source.                                                            | The primary funding source failed but the transaction can be attempted again. The next attempt will use the alternate funding source.                       |
| `unmapped_partner_error`                  | Transaction declined for an unknown reason, please try again later                                                                                       | This decline code has not been mapped in your gateway's Recurly integration. Please reach out to your gateway to address this                               |
| `declined_security_code`                  | The security code (CVV) or expiration date you entered does not match. Please update the CVV/Expiration Date and try again.                              | The payment gateway declined the transaction because the security code (CVV) or expiration date did not match.                                              |
| `roku_zip_code_mismatch`                  | Your billing address does not match the address on your account. Please fix your address or contact your bank.                                           | The payment gateway declined the transaction because the billing address did not match.                                                                     |
| `roku_invalid_card_number`                | Your card number is not valid. Please update your card number.                                                                                           | The credit card number is not valid. The customer needs to try a different number.                                                                          |
| `exceeds_daily_limit`                     | This transaction exceeds your daily approval limit. Please contact your bank or try another card.                                                        | The transaction exceeds the cardholder's daily approval limit.                                                                                              |
| `exceeds_max_amount`                      | The transaction was declined. Please contact support.                                                                                                    | The payment gateway declined the transaction because the withdrawal amount permitted for the shopper's card was exceeded.                                   |
| `issuer_unavailable`                      | The transaction was declined. Please contact support.                                                                                                    | The issuer was unavailable to authorize the transaction. Contact the card issuer or your payment gateway for more details.                                  |
| `payer_authentication_rejected`           | Your card must be authenticated before continuing. Please complete authentication.                                                                       | The authentication flow was not completed or was invalid.                                                                                                   |
| `three_d_secure_connection_error`         | The attempt to authenticate failed due to a connection error. Please try again or try a different payment method.                                        | The authentication flow was not completed or was invalid.                                                                                                   |
| `ach_return`                              | Your transaction was declined. Please contact your bank for further details or try another bank account.                                                 | Transaction was returned (cancelled) by the bank.                                                                                                           |
| `ach_cancel`                              | Your transaction was cancelled. Please contact support for further details.                                                                              | Merchant opted to cancel the transaction.                                                                                                                   |
| `ach_chargeback`                          | Your transaction was cancelled. Please contact your bank for further details.                                                                            | Transaction was cancelled by the consumer.                                                                                                                  |
| `ach_credit_return`                       | Your transaction was declined. Please contact your bank for further details or try another bank account.                                                 | Transaction was returned (cancelled) by the bank.                                                                                                           |
| `ach_validation_exception`                | Information provided was invalid. Please contact support for further details.                                                                            | Account or merchant information provided was invalid.                                                                                                       |
| `ach_exception`                           | The payment system experienced an unspecified error. Please contact support for further details.                                                         | General ACH processing exception.                                                                                                                           |
| `no_gateway_found_for_transaction_amount` | The payment system experienced an error. Your account was not charged. Please contact support for further details.                                       | No gateway credentials with a sufficient single transaction amount limit was found. Please contact the gateway to increase the limit amount.                |
| `merch_max_transaction_limit_exceeded`    | The payment system experienced an error. Your account was not charged. Please contact support for further details.                                       | The limit has been exceeded for your daily or monthly dollar or transactions amount. Please contact the gateway to increase the limit amount.               |
| `batch_processing_error`                  | The payment system experienced an error. Your account was not charged. Please contact support for further details.                                       | An error occurred while preparing the transaction to be processed by the gateway. Please contact support for further details.                               |
| `transaction_stale_at_gateway`            | The payment system experienced an error. Your account was not charged. Please contact support for further details.                                       | An error occurred when sending the transaction to the gateway. Please retry the transaction in order to submit payment to the gateway.                      |
| `invalid_payment_method`                  | Your transaction was declined. Please contact your bank for further details or try another card.                                                         | The transaction was declined by the payment gateway. Contact the payment gateway for more details.                                                          |
| `amazon_declined_review`                  | Your card was declined. In order to resolve the issue, check your payment method in Amazon.                                                              | Declined, Amazon transaction review timed out.                                                                                                              |
| `billing_agreement_replaced`              | Your billing agreement is no longer valid and has been replaced.                                                                                         | The billing agreement is no longer valid and has been replaced, the transaction may be retried.                                                             |

## Configuration

| Code                                 | Customer Message                                                                                                        | Merchant Message                                                                                                                                                                                                        |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `reference_transactions_not_enabled` | Please contact support: the payment system is configured incorrectly. Your PayPal account was not charged.              | Your PayPal account does not have reference transactions enabled. Please contact support.                                                                                                                               |
| `invalid_gateway_configuration`      | Please contact support: the payment system is configured incorrectly. The transaction was not processed.                | Your payment gateway is not configured correctly.  Please contact your payment gateway for more information.                                                                                                            |
| `invalid_login`                      | Please contact support: the payment system is configured incorrectly. The transaction was not processed.                | Your payment gateway login is incorrect. Please check your login credentials.                                                                                                                                           |
| `contact_gateway`                    | Please contact support: the payment system experienced an unspecified error with your card issuer.                      | This error requires you to contact your payment gateway for a resolution.                                                                                                                                               |
| `cvv_required`                       | Please contact support: the payment system experienced an error. Your card was not charged.                             | Your payment gateway account is requiring the security code (CVV) for all transactions. Recurly cannot process recurring/subscription transactions. Please contact your payment gateway to disable the CVV requirement. |
| `currency_not_supported`             | Please contact support: the requested currency is not supported for this merchant. Your card was not charged.           | The currency configured on your Recurly account is not accepted by your gateway. Please use a supported currency or contact your payment gateway for more details.                                                      |
| `ssl_error`                          | Please contact support: the payment system experienced an error. Your card was not charged.                             | Your PEM certificate is configured incorrectly. Recurly cannot communicate with your payment gateway.                                                                                                                   |
| `zero_dollar_auth_not_supported`     | Please contact support: the payment system experienced an error while authorizing your card. Your card was not charged. | Zero dollar authorizations are not supported for this card type or by your payment processor.                                                                                                                           |
| `no_gateway`                         | Please contact support: the payment system experienced an error. Your card was not charged.                             | There is no available payment gateway on your account capable of processing this transaction.                                                                                                                           |
| `gateway_account_setup_incomplete`   | Please contact support: the payment system is configured incorrectly. The transaction was not processed.                | Your payment gateway requires additional setup. Contact your payment gateway for more details.                                                                                                                          |
| `ach_transactions_not_supported`     | Please contact support: ACH/EFT transfers are not supported.                                                            | ACH/EFT transfers are not enabled on your account.                                                                                                                                                                      |
| `three_d_secure_not_supported`       | Please contact support: the payment system experienced an error. Your card was not charged.                             | 3-D Secure was attempted but is not enabled on your account.                                                                                                                                                            |
| `three_d_secure_credential_error`    | Your payment gateway 3DS credentials are missing or incorrect. The card was not charged.                                | The gateway 3DS credentials are missing or incorrect.                                                                                                                                                                   |
| `invalid_gateway_access_token`       | Please contact support: the payment system is configured incorrectly. The transaction was not processed.                | Your payment gateway is not configured correctly.  Please contact support for more information.                                                                                                                         |

## Hard

<Table>
  <thead>
    <tr>
      <th>
        Code
      </th>

      <th>
        Customer Message
      </th>

      <th>
        Merchant Message
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        `paypal_cannot_pay_self`
      </td>

      <td>
        You cannot pay yourself using PayPal. Please use a different PayPal account for the transaction.
      </td>

      <td>
        The PayPal account used to pay is also the merchant account. PayPal does not allow an account to pay itself.
      </td>
    </tr>

    <tr>
      <td>
        `billing_agreement_not_accepted`
      </td>

      <td>
        The transaction failed because you did not accept the PayPal billing agreement. Please try again.
      </td>

      <td>
        The customer did not accept the PayPal billing agreement.
      </td>
    </tr>

    <tr>
      <td>
        `billing_agreement_already_accepted`
      </td>

      <td>
        The PayPal billing agreement failed because you have already accepted the agreement. Please try again or contact support.
      </td>

      <td>
        The customer has already accepted the PayPal billing agreement.
      </td>
    </tr>

    <tr>
      <td>
        `roku_invalid_cib`
      </td>

      <td>
        Your Roku billing agreement is no longer valid. Please update your billing information.
      </td>

      <td>
        The billing agreement is no longer valid. The customer may have canceled the agreement.
      </td>
    </tr>

    <tr>
      <td>
        `recurring_mandate_cancelled`
      </td>

      <td>
        The transaction failed because you have cancelled your mandate with the business.
      </td>

      <td>
        The customer cancelled their mandate. Transactions cannot be sent for cancelled mandates.
      </td>
    </tr>

    <tr>
      <td>
        `declined_exception`
      </td>

      <td>
        Your transaction was declined. Please try again or try another card.
      </td>

      <td>
        An exception occurred with your payment gateway while processing this transaction. The transaction may be missing required information or the information is not properly formatted. Please contact your gateway for details.
      </td>
    </tr>

    <tr>
      <td>
        `declined_missing_data`
      </td>

      <td>
        Your billing information is missing some required information.
      </td>

      <td>
        The payment gateway declined the transaction for missing a required field. Please verify your configuration with Recurly and your gateway is correct. You may need to require more address information.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_data`
      </td>

      <td>
        The transaction was declined due to invalid data.
      </td>

      <td>
        The payment gateway declined the transaction due to invalid data. Please check the response details for more information.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_amount`
      </td>

      <td>
        The transaction was declined. Please contact support.
      </td>

      <td>
        The payment gateway declined the transaction because the total amount was less than the minimum amount allowed by the gateway.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_email`
      </td>

      <td>
        Your email address is not valid.
      </td>

      <td>
        The payment gateway requires a valid email address for this transaction.
      </td>
    </tr>

    <tr>
      <td>
        `declined_card_number`
      </td>

      <td>
        Your card number is not valid. Please update your card number.
      </td>

      <td>
        The credit card number is not valid. The customer needs to try a different number.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_card_number`
      </td>

      <td>
        Your card number is not valid. Please update your card number.
      </td>

      <td>
        The credit card number is not valid. The customer needs to try a different number.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_account_number`
      </td>

      <td>
        Your account number is not valid. Please update your account number.
      </td>

      <td>
        The account number is not valid. The customer needs to try a different number.
      </td>
    </tr>

    <tr>
      <td>
        `gateway_token_not_found`
      </td>

      <td>
        Your payment details were not found. Please update your billing information.
      </td>

      <td>
        The payment details were not found in your payment gateway. The customer needs to update their billing information.
      </td>
    </tr>

    <tr>
      <td>
        `expired_card`
      </td>

      <td>
        Your credit card is expired, please update your card.
      </td>

      <td>
        The payment gateway declined the transaction because the expiration date is expired or does not match.
      </td>
    </tr>

    <tr>
      <td>
        `declined_expiration_date`
      </td>

      <td>
        Your expiration date is invalid or does not match.
      </td>

      <td>
        The payment gateway declined the transaction because the expiration date is expired or does not match.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_merchant_type`
      </td>

      <td>
        Your card is not allowed to complete this transaction. Please try another card.
      </td>

      <td>
        The card is not allowed to make purchases from you (e.g. a Travel only card trying to purchase electronics).
      </td>
    </tr>

    <tr>
      <td>
        `invalid_transaction`
      </td>

      <td>
        Your card is not allowed to complete this transaction. Please contact your bank or try another card.
      </td>

      <td>
        The card type cannot perform the transaction type. The card is likely restricted. The customer needs to contact their bank for details.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_issuer`
      </td>

      <td>
        Your card number is not valid. Please try another card or contact your bank.
      </td>

      <td>
        The card number references an issuer (bank) that does not exist.  It is not a valid card number.
      </td>
    </tr>

    <tr>
      <td>
        `card_type_not_accepted`
      </td>

      <td>
        Your card type is not accepted. Please try another card.
      </td>

      <td>
        Your merchant account does not accept this card type or specific transaction.
      </td>
    </tr>

    <tr>
      <td>
        `payment_not_accepted`
      </td>

      <td>
        Your payment type is not accepted. Please try another card.
      </td>

      <td>
        Your merchant account does not accept this payment type or specific transaction.
      </td>
    </tr>

    <tr>
      <td>
        `restricted_card`
      </td>

      <td>
        Your card cannot be accepted. Please contact your issuing bank for details or try another card.
      </td>

      <td>
        The card number has restrictions that prevent it from being used with your merchant account. It is likely a corporate card. The customer needs to use a different card.
      </td>
    </tr>

    <tr>
      <td>
        `restricted_card_chargeback`
      </td>

      <td>
        Your card cannot be accepted. Please contact your issuing bank for details or try another card.
      </td>

      <td>
        The card has a restriction preventing approval if there are any chargebacks against it.
      </td>
    </tr>

    <tr>
      <td>
        `card_not_activated`
      </td>

      <td>
        Your card has not been activated.  Please call your bank to activate your card and try again.
      </td>

      <td>
        The card is brand new and has not been activated yet.
      </td>
    </tr>

    <tr>
      <td>
        `deposit_referenced_chargeback`
      </td>

      <td>
        The refund cannot be processed because of a chargeback.
      </td>

      <td>
        The deposit is already referenced by a chargeback; therefore, a refund cannot be processed against this transaction.
      </td>
    </tr>

    <tr>
      <td>
        `customer_canceled_transaction`
      </td>

      <td>
        You canceled the transaction after it was approved. Please update your billing information to authorize a new transaction.
      </td>

      <td>
        The cardholder requested this particular payment be stopped before it settled.
      </td>
    </tr>

    <tr>
      <td>
        `cardholder_requested_stop`
      </td>

      <td>
        You requested recurring payments no longer be accepted on this card. Please update your billing information.
      </td>

      <td>
        The cardholder requested recurring payments be stopped. This card will no longer work with your merchant account.
      </td>
    </tr>

    <tr>
      <td>
        `roku_invalid_payment_method`
      </td>

      <td>
        Your billing information is no longer valid. Please update your billing information.
      </td>

      <td>
        The transaction was declined by the payment gateway. Contact the card issuer for more details.
      </td>
    </tr>

    <tr>
      <td>
        `rjs_token_expired`
      </td>

      <td>
        Payment was not processed. Please re-enter your billing information.
      </td>

      <td>
        The token for this transaction either expired or has already been used. Please advise the customer to re-enter billing information to obtain a new token.
      </td>
    </tr>

    <tr>
      <td>
        `card_blocked`
      </td>

      <td>
        You requested charges from this merchant no longer be accepted on this card. Please update your billing information.
      </td>

      <td>
        The cardholder requested payments be stopped. This card will no longer work with your merchant account.
      </td>
    </tr>

    <tr>
      <td>
        `lifecycle_decline`
      </td>

      <td>
        Please re-enter your billing information.
      </td>

      <td>
        Please advise customer to re-enter billing information.
      </td>
    </tr>

    <tr>
      <td>
        `no_billing_information`
      </td>

      <td>
        Your billing information is not on file. Please add your billing information.
      </td>

      <td>
        This transaction cannot be processed because Recurly has no billing information for this account.
      </td>
    </tr>

    <tr>
      <td>
        `paypal_invalid_billing_agreement`
      </td>

      <td>
        Your PayPal billing agreement is no longer valid. Please update your billing information.
      </td>

      <td>
        The billing agreement is no longer valid. The customer may have canceled the agreement.
      </td>
    </tr>

    <tr>
      <td>
        `paypal_hard_decline`
      </td>

      <td>
        Your primary funding source was declined. Please update your billing information with PayPal or try again.
      </td>

      <td>
        PayPal failed to run the transaction with the primary funding source.
      </td>
    </tr>

    <tr>
      <td>
        `paypal_account_issue`
      </td>

      <td>
        Your primary funding source was declined. Please update your billing information with PayPal or try again.
      </td>

      <td>
        PayPal indicated the transaction failed due to an issue with the buyer account.
      </td>
    </tr>

    <tr>
      <td>
        `paypal_expired_reference_id`
      </td>

      <td>
        Your billing information is no longer valid. Please update your billing information.
      </td>

      <td>
        The Reference ID refers to a transaction that is more than 365 days old.
      </td>
    </tr>

    <tr>
      <td>
        `contract_not_found`
      </td>

      <td>
        The billing info for this account has not been verified, please wait 24 hours and try again.
      </td>

      <td>
        The contract has not been finalized for this payment type. Please wait until the contract is finalized to add another subscription or transaction. Or, re-insert the billing info.
      </td>
    </tr>

    <tr>
      <td>
        `gateway_validation_exception`
      </td>

      <td>
        One or more values submitted did not pass a gateway specific validation. Please contact support to learn the cause.
      </td>

      <td>
        A gateway validation error has been triggered by the customer's input values. Please contact support for further assistance.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_name`
      </td>

      <td>
        You must provide a first and last name.
      </td>

      <td>
        The payment gateway requires a valid first and last name for this transaction.
      </td>
    </tr>

    <tr>
      <td>
        `direct_debit_type_not_accepted`
      </td>

      <td>
        Your direct debit type is not accepted. Please try another direct debit type / currency combination.
      </td>

      <td>
        Your merchant account does not accept this direct debit type / currency combination.
      </td>
    </tr>

    <tr>
      <td>
        `three_d_secure_action_result_token_mismatch`
      </td>

      <td>
        An error occurred while processing your transaction. Please contact support.
      </td>

      <td>
        Expected token does not match the action that created it.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_not_found`
      </td>

      <td>
        The original transaction was not found.
      </td>

      <td>
        The original transaction was not found.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_settled`
      </td>

      <td>
        The transaction has already been settled, so it cannot be voided. Please try a refund.
      </td>

      <td>
        The transaction has already been settled, so it cannot be voided. Please try a refund.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_already_voided`
      </td>

      <td>
        The transaction has already been voided, so it cannot be settled or refunded.
      </td>

      <td>
        The transaction has already been voided, so it cannot be settled or refunded.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_failed_to_settle`
      </td>

      <td>
        The transaction did not settle successfully. Please update your billing information.
      </td>

      <td>
        The transaction authorized successfully, but failed to settle. The settlement request may have expired or have been canceled.
      </td>
    </tr>

    <tr>
      <td>
        `payment_cannot_void_authorization`
      </td>

      <td>
        An error occurred while voiding your payment authorization. Please contact support.
      </td>

      <td>
        An error occurred while voiding the payment authorization.
      </td>
    </tr>

    <tr>
      <td>
        `partial_credits_not_supported`
      </td>

      <td>
        An error occurred while refunding your transaction. Please contact support.
      </td>

      <td>
        Your payment gateway does not support partially refunding a transaction. Please refund the entire amount.
      </td>
    </tr>

    <tr>
      <td>
        `cannot_refund_unsettled_transactions`
      </td>

      <td>
        An error occurred while refunding your transaction. Please contact support.
      </td>

      <td>
        The transaction has not settled yet, so it cannot be refunded.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_cannot_be_refunded`
      </td>

      <td>
        An error occurred while refunding your transaction. Please contact support.
      </td>

      <td>
        The transaction cannot be refunded. Please contact your payment gateway for details.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_cannot_be_voided`
      </td>

      <td>
        The transaction cannot be voided. Please contact support.
      </td>

      <td>
        The transaction cannot be voided. It may have settled, already been voided, or otherwise be ineligible for voiding.
      </td>
    </tr>

    <tr>
      <td>
        `total_credit_exceeds_capture`
      </td>

      <td>
        An error occurred while refunding your transaction. Please contact support.
      </td>

      <td>
        The credit exceeds the amount of the original transaction.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_already_refunded`
      </td>

      <td>
        The transaction has already been refunded.
      </td>

      <td>
        The transaction has already been refunded.
      </td>
    </tr>

    <tr>
      <td>
        `authorization_expired`
      </td>

      <td>
        An error occurred while processing your transaction. Please update your billing information.
      </td>

      <td>
        The purchase authorization expired and can no longer be used to collect payment. Please attempt another transaction.
      </td>
    </tr>

    <tr>
      <td>
        `authorization_already_captured`
      </td>

      <td>
        An error occurred while processing your transaction. Please contact support.
      </td>

      <td>
        The purchase amount was already captured. This authorization cannot be used again.
      </td>
    </tr>

    <tr>
      <td>
        `authorization_amount_depleted`
      </td>

      <td>
        An error occurred while processing your transaction. Please contact support.
      </td>

      <td>
        The amount of purchases exceeds the original authorized amount.  You cannot collect more money using this authorization.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_cannot_be_authorized`
      </td>

      <td>
        An error occurred while processing your transaction. Please contact support.
      </td>

      <td>
        Authorization is not supported by this payment gateway.
      </td>
    </tr>

    <tr>
      <td>
        `transaction_cannot_be_refunded_currently`
      </td>

      <td>
        The transaction cannot be refunded at this time. Please try again later.
      </td>

      <td>
        The transaction cannot be refunded at this time. Please try again later.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_billing_agreement_status`
      </td>

      <td>
        Your billing agreement is no longer valid. Please update your billing information.
      </td>

      <td>
        The billing agreement is no longer valid. The customer may have canceled the agreement.
      </td>
    </tr>

    <tr>
      <td>
        `billing_agreement_not_found`
      </td>

      <td>
        Your billing agreement is no longer valid. Please update your billing information.
      </td>

      <td>
        The billing agreement is no longer valid. The customer may have canceled the agreement.
      </td>
    </tr>

    <tr>
      <td>
        `invalid_payment_method_hard`
      </td>

      <td>
        Your transaction was declined. Please contact your bank for further details or try another card.
      </td>

      <td>
        The transaction was declined by the payment gateway. Contact the payment gateway for more details.
      </td>
    </tr>

    <tr>
      <td>
        `recurring_mandate_cancelled`
      </td>

      <td>
        The transaction failed because you have cancelled your mandate with the business.

      </td>

      <td>
        The customer cancelled their mandate. Transactions cannot be sent for cancelled mandates.

      </td>
    </tr>
  </tbody>
</Table>

## Fraud

| Code                          | Customer Message                                                                                                    | Merchant Message                                                                                                                                                                                  |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `fraud_address`               | Your billing address does not match the address on your account. Please update your address or contact your bank.   | The payment gateway declined the transaction because the billing address did not match.                                                                                                           |
| `fraud_security_code`         | The security code you entered does not match. Please update the CVV and try again.                                  | The payment gateway declined the transaction because the security code (CVV) or expiration date did not match.                                                                                    |
| `fraud_stolen_card`           | The transaction was declined. Please use a different card or contact your bank.                                     | The card has been designated as lost or stolen; contact the issuing bank.                                                                                                                         |
| `fraud_ip_address`            | The transaction was declined. Please contact support.                                                               | The payment gateway declined the transaction because it originated from an IP address known for fraudulent transactions.                                                                          |
| `fraud_gateway`               | The transaction was declined. Please use a different card, contact your bank, or contact support.                   | The payment gateway declined the transaction due to fraud filters enabled in your gateway.                                                                                                        |
| `fraud_too_many_attempts`     | You attempted to use this card too many times. Please wait 15 minutes before trying again, or use a different card. | The card number was used unsuccessfully too many times consecutively.  The cardholder must wait before the card number will work again.                                                           |
| `fraud_advanced_verification` | The transaction was declined. Please use a different card or contact your bank.                                     | The payment gateway declined the transaction because it failed the advanced verification.                                                                                                         |
| `fraud_velocity`              | The transaction was declined. Please contact support.                                                               | The transaction was part of a high-volume from a single source, indicating possible fraudulent activity.                                                                                          |
| `fraud_generic`               | Please validate information and try again. If the problem persists, please contact your bank.                       | The payment gateway declined the transaction because it was flagged for potential fraud. The customer needs to contact their bank or you may need to contact your gateway to learn more.          |
| `fraud_address_recurly`       | Your billing address does not match the address on your account. Please fix your address or contact your bank.      | Recurly declined the transaction because the billing address did not match the address on the bank records.                                                                                       |
| `fraud_risk_check`            | This transaction was declined. Please contact your bank or try a different card.                                    | Fraudulent Transaction: This transaction was declined based on your fraud management settings. Please see the "Fraud Details" section on the transaction details page for additional information. |
| `fraud_manual_decision`       | This transaction was declined. Please contact your bank or try a different card.                                    | Fraudulent: This transaction was marked as fraudulent in Kount. Please see the Fraud Details section on the transaction for more details.                                                         |

## Communication

| Code                                 | Customer Message                                                                                   | Merchant Message                                                                                                                                                    |
| ------------------------------------ | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `gateway_unavailable`                | Please contact support: the payment system experienced an unspecified error with your card issuer. | The payment gateway was unavailable for transaction. Contact your payment gateway for more details.                                                                 |
| `processor_unavailable`              | Please contact support: the payment system experienced an unspecified error with your card issuer. | The payment processor was unavailable for the transaction. Contact your payment gateway for more details.                                                           |
| `gateway_timeout`                    | Please contact support: the payment system did not respond in time to process your transaction.    | The payment gateway timed out while processing this transaction. Please verify that the transaction did not process. Contact your payment gateway for more details. |
| `gateway_error`                      | An error occurred while processing your transaction. Please contact support.                       | The payment gateway encountered an unknown error. Please contact your payment gateway for details.                                                                  |
| `too_busy`                           | Please try your transaction again.                                                                 | The payment gateway is too busy or experienced another temporary problem, and cannot process the transaction at the moment. Please try again.                       |
| `gateway_rate_limited`               | Please contact support: the payment system is rate limiting requests.                              | The payment gateway is rate limiting your requests. Contact your payment gateway for more details.                                                                  |
| `moneybot_unavailable`               | Please try again in a few minutes.                                                                 | Payment gateway service is unavailable. Please try again in a few minutes.                                                                                          |
| `moneybot_disconnect`                | An error occurred while processing your transaction. Please contact support.                       | An error occurred while processing the transaction. Please contact Recurly support.                                                                                 |
| `transaction_service_v2_unavailable` | Please try again in a few minutes.                                                                 | Payment gateway service is unavailable. Please try again in a few minutes.                                                                                          |
| `transaction_service_v2_disconnect`  | An error occurred while processing your transaction. Please contact support.                       | An error occurred while processing the transaction. Please contact Recurly support.                                                                                 |

## ThreeDSecureRequired

| Code                            | Customer Message                                                   | Merchant Message                                                                      |
| ------------------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| `three_d_secure_authentication` | Your card must be authenticated with 3-D Secure before continuing. | Your payment gateway is requesting that the transaction be completed with 3-D Secure. |

## ThreeDSecureActionRequired

| Code                             | Customer Message                                                   | Merchant Message                                                                      |
| -------------------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| `three_d_secure_action_required` | Your card must be authenticated with 3-D Secure before continuing. | Your payment gateway is requesting that the transaction be completed with 3-D Secure. |

## Amazon

| Code                                    | Customer Message                                                             | Merchant Message                                                                                               |
| --------------------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `amazon_invalid_authorization_status`   | An error occurred while processing your transaction. Please contact support. | You attempted to capture or close an authorization that is in a state where a capture or close is not allowed. |
| `amazon_invalid_close_attempt`          | An error occurred while processing your transaction. Please contact support. | You attempted to close an object that cannot be closed in its current state.                                   |
| `amazon_invalid_order_status`           | An error occurred while processing your transaction. Please contact support. | You attempted to call an operation on an order that is in a state where the operation is not supported.        |
| `amazon_invalid_create_order_reference` | An error occurred while processing your transaction. Please contact support. | You attempted to close an object that cannot be closed in its current state.                                   |
| `amazon_order_not_modifiable`           | An error occurred while processing your transaction. Please contact support. | The order reference is confirmed and can no longer be modified.                                                |
| `amazon_amount_exceeded`                | An error occurred while processing your transaction. Please contact support. | The amount authorized or captured exceeds the amount available.                                                |
| `amazon_transaction_count_exceeded`     | An error occurred while processing your transaction. Please contact support. | The number of authorizations, captures or refunds has exceeded the maximum allowed limit.                      |
| `amazon_not_authorized`                 | An error occurred while processing your transaction. Please contact support. | The billing agreement is encountering authorization issues.                                                    |

## Unknown

| Code            | Customer Message                                                                                    | Merchant Message                                                                                   |
| --------------- | --------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `recurly_error` | An error occurred while processing your transaction. Please contact support.                        | An error occurred while processing the transaction. Please contact Recurly support.                |
| `unknown`       | Your transaction was declined or failed for an unknown reason. Please try again or contact support. | The transaction was declined or failed for an unknown reason. Please try again or contact support. |

## ApiError

| Code        | Customer Message                                                             | Merchant Message                                                                                                              |
| ----------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `api_error` | An error occurred while processing your transaction. Please contact support. | The payment gateway returned an error code that usually indicates its API specs have changed. Please contact Recurly support. |

## Duplicate

| Code                    | Customer Message                                                                       | Merchant Message                                                                                                                                                                                                    |
| ----------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `duplicate_transaction` | A similar transaction was recently submitted. Please wait a few minutes and try again. | A transaction was recently submitted with the same Invoice Number, or the same account/card number and amount. The payment gateway refused to process this transaction in order to prevent a duplicate transaction. |

## Skles

| Code                            | Customer Message                                                             | Merchant Message                                                                    |
| ------------------------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `vaultly_service_unavailable`   | Please try again in a few minutes.                                           | Encryption service is unavailable. Please try again in a few minutes.               |
| `recurly_failed_to_get_token`   | An error occurred while initializing the transaction. Please try again.      | An error occurred while initializing the transaction. Please try again.             |
| `recurly_token_not_found`       | An error occurred while processing your transaction. Please contact support. | An error occurred while processing the transaction. Please contact Recurly support. |
| `recurly_credentials_not_found` | An error occurred while processing your transaction. Please contact support. | An error occurred while processing the transaction. Please contact Recurly support. |
| `recurly_token_mismatch`        | An error occurred while processing your transaction. Please contact support. | An error occurred while processing the transaction. Please contact Recurly support. |

# Examples

Below is an example of Recurly’s XML and JSON error responses for a CVV mismatch (`fraud_security_code`).

```xml
<?xml version="1.0" encoding="UTF-8"?>
<errors>
  <transaction_error>
    <error_code>fraud_security_code</error_code>
    <error_category>fraud</error_category>
    <merchant_message>The payment gateway declined the transaction because the security code (CVV) did not match.</merchant_message>
    <customer_message>The security code you entered does not match. Please update the CVV and try again.</customer_message>
    <gateway_error_code>301</gateway_error_code>
  </transaction_error>
  <error field="transaction.account.billing_info.verification_value" symbol="declined_bad">did not match</error>
  <transaction href="https://your-subdomain.recurly.com/v2/transactions/3d1c6aa86e3d447eb0f3b4a6e3e074d9" type="credit_card">
    <uuid>3d1c6aa86e3d447eb0f3b4a6e3e074d9</uuid>
    <action>purchase</action>
    <amount_in_cents type="integer">4900</amount_in_cents>
    <tax_in_cents type="integer">0</tax_in_cents>
    <currency>USD</currency>
    <status>declined</status>
    <reference nil="nil"></reference>
    <test type="boolean">true</test>
    <voidable type="boolean">false</voidable>
    <refundable type="boolean">false</refundable>
    <transaction_error>
      <error_code>fraud_security_code</error_code>
      <error_category>fraud</error_category>
      <merchant_message>The payment gateway declined the transaction because the security code (CVV) did not match.</merchant_message>
      <customer_message>The security code you entered does not match. Please update the CVV and try again.</customer_message>
      <gateway_error_code>123</gateway_error_code>
    </transaction_error>
    <cvv_result code="N">No Match</cvv_result>
    <avs_result code="D">Street address and postal code match.</avs_result>
    <avs_result_street>Y</avs_result_street>
    <avs_result_postal>Y</avs_result_postal>
    <created_at type="datetime">2011-10-17T17:24:53Z</created_at>
    <details>
      <account>
        <account_code>1</account_code>
        <first_name nil="nil"></first_name>
        <last_name nil="nil"></last_name>
        <company nil="nil"></company>
        <email>verena@example.com</email>
        <billing_info type="credit_card">
          <first_name nil="nil"></first_name>
          <last_name nil="nil"></last_name>
          <address1 nil="nil"></address1>
          <address2 nil="nil"></address2>
          <city nil="nil"></city>
          <state nil="nil"></state>
          <zip nil="nil"></zip>
          <country nil="nil"></country>
          <phone nil="nil"></phone>
          <vat_number nil="nil"></vat_number>
          <card_type>Visa</card_type>
          <year type="integer">2015</year>
          <month type="integer">11</month>
          <first_six>400000</first_six>
          <last_four>0101</last_four>
        </billing_info>
      </account>
    </details>
  </transaction>
</errors>
```
```json
{
  "error": {
    "type": "transaction",
    "message": "The security code you entered does not match. Please update the CVV and try again.",
    "params": [],
    "transaction_error": {
      "object": "transaction_error",
      "transaction_id": "ot9lv264n9dz",
      "category": "fraud",
      "code": "fraud_security_code",
      "message": "The security code you entered does not match. Please update the CVV and try again.",
      "merchant_advice": "The payment gateway declined the transaction because the security code (CVV) or expiration date did not match.",
      "three_d_secure_action_token_id": null
    }
  }
}
```
