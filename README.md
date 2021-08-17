# Introduction

The aiqa-health reseller api is a JSON API that surfaces all of the activities of a reseller.

## Open Endpoints

Open endpoints require no Authentication.

- [Send/Resend Otp](otp/send.md) : `POST /otp/send`
- [Verify Otp](otp/verify.md) : `POST /otp/verify`
- [Check Pincode](check-pin.md) : `GET /check-pin/:pincode`

## Endpoints that require Authentication

Closed endpoints require a valid Token to be included in the header of the request. A Token can be acquired from the OTP endpoints above or can be get from reseller panel.

### Reseller and Subscription

Endpoint manipulates or displays information related to the reseller whose token is provided with the request:

- [Profile](reseller/me.md) : `GET /me`
- [Subscriptions](subscription/subscriptions.md) : `GET /subscriptions`
- [New Subscription](subscription/subscribe.md) : `POST /subscribe`
- [Subscription Detail](subscription/subscription.md) : `GET /subscription/:id`
- [Products](subscription/products.md) : `GET /products`
- [Questions](subscription/questions.md) : `GET /questions`

### VPA Mandate and Payment

Endpoints to register/check vpa mandate request and send payment link or check payment.

- [Vpa Register](vpa/register.md) : `POST /vpa/register`
- [Vpa Enquiry](vpa/enquiry.md) : `POST /vpa/enquiry`
- [Payment Link](payment/send-link.md) : `POST /payment/send-link`
- [Payment Check](payment/check.md) : `GET /payment/check/:id`