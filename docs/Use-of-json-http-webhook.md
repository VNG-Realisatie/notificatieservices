# Guideline for use of JSON, HTTP en Webhook

## Introduction

The CloudEvent-NL message format can be used when using different formats and protocols. CloudEvents has a [layered architecture](https://github.com/cloudevents/spec/blob/v1.0.1/primer.md#architecture) for this. Agreements must be made about how the GOV-NL profile should be used when using a specific format or protocol.

In addition to the CloudEvent specification the [Serverless Working Group](https://github.com/cncf/wg-serverless) has described for different formats and protocols how they can be used in a standardized way in combination with the CloudEvents message format. A description of common formats and protocols can be found at: https://github.com/cloudevents/spec#cloudevents-documents.

Within the Dutch government, frequent use is made of the JSON format, the HTTP protocol and the Webhook pattern for data exchange. For example, a common way to send events to consumers is to use a webhook where a message in JSON format is sent via the HTTP protocol. Further standardization than just event description therefore benefits most from agreements around these 3 areas. In addition to standardization through the use of the NL GOV profile, we
therefore work towards standardization on using JSON, HTTP and Webhook.

The NL GOV profile is intended as a formal government-wide standard to be used. This does not yet apply to the additional specification for the use of JSON, HTTP and Webhook. The specifications for them therefore have the character of a 'guideline' ("a statement by which to determine a course of action", [Wikipedia](https://en.wikipedia.org/wiki/Guideline)).

When using the NL GOV profile in combination with JSON, HTTP or Webhook, the following specifications SHOULD be used:

- [JSON Event Format for CloudEvents](https://github.com/cloudevents/spec/blob/v1.0.1/json-format.md): The JSON Format for CloudEvents defines how events are expressed in JavaScript Object Notation (JSON) Data Interchange Format [RFC8259](https://tools.ietf.org/html/rfc8259).
- [HTTP Protocol Binding for CloudEvents](https://github.com/cloudevents/spec/blob/v1.0.1/http-protocol-binding.md): The HTTP Protocol Binding for CloudEvents defines how events are mapped to HTTP 1.1 request and response messages.
- [HTTP 1.1 Web Hooks for Event Delivery](https://github.com/cloudevents/spec/blob/v1.0.1/http-webhook.md): The specification aims to provide a definition for use with CNCF CloudEvents, but is considered generally usable beyond the scope of CloudEvents.

A number of comments are made below in response to the three specifications. These are intended to make use more unambiguous and to work towards formal standardisation in the long term.

## JSON

todo

## HTTP

todo

## Webhook

todo

## Normative References

- [CloudEvents Specification](https://github.com/cloudevents/spec/blob/v1.0.1/json-format.md)
- [JSON Event Format for CloudEvents - Version 1.0.1](https://github.com/cloudevents/spec/blob/v1.0.1/json-format.md)
- [HTTP Protocol Binding for CloudEvents - Version 1.0.1](https://github.com/cloudevents/spec/blob/v1.0.1/http-protocol-binding.md)
- [HTTP 1.1 Web Hooks for Event Delivery - Version 1.0.1](https://github.com/cloudevents/spec/blob/v1.0.1/http-webhook.md)
