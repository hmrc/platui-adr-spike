# 2. play-frontend-hmrc mirrors hmrc-frontend

Date: 2020-10-19

## Status

Accepted

## Context

The need to provide an HMRC footer translated into Welsh (PLATUI-752), facing the lack of 
support for Welsh in the GDS govukFooter component,

## Decision

We will maintain parity between hmrc-frontend and play-frontend-hmrc
except for helper components that will not contain significant presentational markup.

## Consequences

Maintain separation of concerns between hmrc-frontend and play-frontend-hmrc

Maintain conceptual integrity of play-frontend-hmrc

Be able to test markup using existing test strategy

We will need to add and maintain a new hmrcFooter component into
hmrc-frontend and play-frontend-hmrc providing a mirror of govukFooter with localised content,
 
We will need to create a new `helpers` package within play-frontend-hmrc to clearly demarcate them
from presentational components,

We will need to redesign the existing hmrcFooter helper to wrap the new hmrcFooter component
 and move to the helpers package,

The new hmrcFooter component will need to be deprecated when GDS provide a localised version
of govukFooter,

We will need to liaise and get approval from the HMRC design system team for adding
hmrcFooter to the hmrc/design-system and hmrc/hmrc-frontend

We will be adding features that are unlikely to be useful or used by designers because
 at the prototyping phase content is not stable enough for translation into Welsh
