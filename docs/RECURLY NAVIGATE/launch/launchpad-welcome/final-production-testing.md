---
title: 'Section 1: Final Production Testing'
excerpt: >-
  Walk through production testing, a quick final check of your subscription
  payment flow that ensures your site is customer-ready.
deprecated: false
hidden: true
metadata:
  robots: index
next:
  description: >-
    Click "Section 2: Dunning Optimization" to learn how to strategically
    configure your Dunning settings. 
  pages:
    - slug: dunning-optimization
      title: 'Section 2: Dunning Optimization'
      type: basic
---
# Trail Guide: Final Production Testing

It's vital to experience your customer's checkout journey from start to finish before going live — and it gives you a chance to catch potential payment issues along the way.

Watch this quick Navigate Trail Guide to learn how to run a real transaction, issue a refund, and be sure payments are working (so your customers don't find them first). For written reference, you'll find a step-by-step checklist at the bottom of this page.

<HTMLBlock>{`
<div id="trailguide"style="position:relative;overflow:hidden;aspect-ratio:1920/1080"><iframe src="https://share.synthesia.io/embeds/videos/f3384551-b4b2-4ab3-83fa-c8fe6e88c62f" title="Synthesia video player - Navigate Trail Guide: Check the boxes: final production test" allowfullscreen="" allow="encrypted-media; fullscreen; microphone; screen-wake-lock;" style="position:absolute;width:100%;height:100%;top:0;left:0;border:none;padding:0;margin:0;overflow:hidden"></iframe></div>
`}</HTMLBlock>

<HTMLBlock>{`
<p style="display: none;"
              Navigate Trail Guide
              Launchpad: Check the boxes — Final test in production

              Welcome to Launchpad, part of the Recurly Navigate program! This collection of actionable guides is designed to ignite your Recurly liftoff.

              This program helps optimize and prepare for continued success, boosting subscription businesses from production into transaction, and beyond.

              Today, we'll kick off with a quick final test in production. It's best practice to do this before customers visit your site. After completing these few steps, you are ready for liftoff!

              Open your favorite checkout page, grab your card, and walk through the payment process like a real customer.

              Remember, help is available right inside of your Recurly App. If at any point during this Trail Guide you need additional context, you can use the "AI Answers" tool, click the "Recurly Resources" button, or open the Chatbot. And of course, you can always navigate to support.recurly.com for more options.

              Now let's get started!

              Steps for Final Test in Production:
              • Find your product and head to checkout.
              • Complete the form, making sure to include all required information on the checkout page.
              • Subscribe.
              • Open your Recurly app and make sure the payment was successful.
              • Issue a refund for that transaction to check that it goes through.
              • If you are based in the EU, remember to complete a test payment with 3D Secure to ensure SCA compliance.

              Review of Steps:
              • Subscribe to your own service or product using a real card.
              • Check that the payment was finalized.
              • Issue a refund, making sure it completes.
              • If you are in the EU, test your SCA compliance with 3D Secure.
              • For comprehensive 3D compliance documentation, refer to the relevant resources.

              Troubleshooting Failed Payments:

              Did something fail? The usual culprits are your payment gateway or checkout page. Refer to documentation to help test your gateway and double-check your checkout page. This should help identify the most common issues with configuration. If neither of those solve the problem, your next best step is to open a support ticket.

              Your site is now tested and customer-ready!

              Thanks for joining for this Navigate Launchpad video! The Navigate program helps optimize dunning setup and strategy for maximum revenue recovery.
              /p>
`}</HTMLBlock>

<br />

<Callout icon="🖐️" theme="default">
  **Find a hiccup?** Double check your **[gateway](https://docs.recurly.com/recurly-subscriptions/docs/test)** and **<Anchor label="checkout" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/checkout#configuration-landing-page">checkout</Anchor>** configurations. If manual troubleshooting doesn't do the trick, Support is your best next step: **<Anchor label="contact support" target="_blank" href="mailto:support@recurly.com">contact support</Anchor>.** 
</Callout>

<br />

# 3DS Compliance

**European Merchants**: The comprehensive documentation below will help you prepare for 3DS compliance and finalize your production testing. 

<Anchor label="https://docs.recurly.com/recurly-subscriptions/docs/revised-payment-services-directive-psd2" target="_blank">https://docs.recurly.com/recurly-subscriptions/docs/revised-payment-services-directive-psd2</Anchor>

<br />

<br />

# Final Production Testing: Step-by-Step

**Use this checklist** to ensure you've taken all of the necessary steps to complete Final Production Testing. If you have any trouble finding what you need, refer back to "**[Trail Guide: Final Production Testing](#trailguide)**" for guidance.

* [ ] **1. Complete a Live Checkout Test:** Choose a live checkout page and purchase a product or subscription using a real card, then confirm the checkout completes successfully.
* [ ] **2. Verify the Payment in Recurly:** Log in to your Recurly App and confirm the test transaction shows a successful payment.
* [ ] **3. Issue and Confirm a Refund:** Refund the test transaction in Recurly and confirm the refund processes successfully.
* [ ] **4. (EU Only) Test 3D Secure / SCA Compliance:** Complete a test payment using 3D Secure to confirm your checkout meets SCA requirements.
* [ ] **5. Troubleshoot if a Step Fails:** Review your payment gateway and checkout configuration using the provided documentation, and contact support if issues persist.

## What a way to start!

Nice work! Final production testing helps ensure everything functions as expected before real customers interact with your setup. Your site is now tested and ready for subscriptions. 

Up next, we’ll focus on Dunning optimization to help you recover failed payments and reduce involuntary churn.

<br />
