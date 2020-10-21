# 3. Use id to identify the tracking consent script tag

Date: 2020-10-19

## Status

Accepted

## Context

The need to inject configuration into the tracking consent snippet (PLATUI-775 and PLATUI-649)
while not wanting to duplicate knowledge of the platform and tracking consent url structure, 
delivering a simple, easily testable solution and delivering a solution that works on IE.

## Decision

We will use data attributes for configuration parameters and to use an identifier to locate the tracking consent
 SCRIPT tag rather than using regular expression pattern matching on the SCRIPT src attribute

## Consequences

A flexible DRY solution that will withstand changes to url paths, port numbers,
and platform environment naming.

Service developers will need to add this identifier to the SCRIPT tag albeit with the
 assistance of a helper.
