# Use an id and data attributes on the SCRIPT tag for configuration

* Status: accepted
* Date: 2020-10-19

## Context and Problem Statement

The need to inject configuration into the tracking consent snippet (PLATUI-775 and PLATUI-649)
while not wanting to duplicate knowledge of the platform and tracking consent url structure, 
delivering a simple, easily testable solution and delivering a solution that works on IE.

## Decision Drivers

* not wanting to duplicate knowledge of the platform and tracking consent url structure, 
* delivering a simple, easily testable solution and
* delivering a solution that works on IE

## Considered Options

* Regular expression pattern matching on SCRIPT src attribute
* Identifier attribute on the SCRIPT tag

## Decision Outcome

Chosen option: "identifier attribute", because positives outweigh negatives (see below).

### Positive Consequences

* Solution is more flexible and more likely to withstand changes to url paths, port numbers,
and platform environment naming.
* Solution is simpler and easier to test and verify.

### Negative Consequences

* Service developers will need to add this identifier to the SCRIPT tag albeit with the
   assistance of a helper.
