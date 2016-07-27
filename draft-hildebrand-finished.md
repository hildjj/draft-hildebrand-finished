---
title: Mark Internet-Drafts as finished
abbrev: finished
docname: draft-hildebrand-finished
date:
category: std
ipr: trust200902

author:
 -
    ins: J. Hildebrand
    name: Joe Hildebrand
    organization: Cisco Systems
    email: jhildebr@cisco.com

--- abstract

Describes a mechanism to mark an Internet-Draft as "finished", removing the
"Expires" information and prohibiting further versions of that draft from
being published.

--- middle

# Introduction

Sometimes, authors want to make a document available to the Internet community
that will have a long lifetime, but do not want to go through a full standards
review.  Now that the Internet-Draft repository does not remove drafts as they
expire, writing an Internet-Draft is a lightweight mechanism for publishing
such documents.

Today, if an author wants an Internet-Draft to appear unexpired, they have to
publish a new version at least once every six months.  For documents that are
"finished" (See {{finished}}), this document proposes that the draft be marked
in a way that is easily distinguishable from drafts that are still works in
progress.

There are several motivations for this capability:

* The desire to publish stable documents that the Independent Stream Editor
  is unwilling to publish as RFCs.
* The need to distinguish documents without consensus or review from the more
  formal outputs of the Internet community.

# What "finished" means {#finished}

A "finished" draft is one where the author promises to publish no further
revisions of a document with the same name to the Internet-Draft repository.
Further inferences, customs, and best practices may evolve over time regarding
when to mark a draft as "finished".

Documents that are "finished" are not different from other Internet-Drafts in
that they do not represent the consensus of any portion of the Internet
Community.  They might, at the option of a stream manager, be published as
RFCs using the normal mechanisms; however, trying to publish a "finished"
draft is likely to be frustrating since there is no easy way to capture the
changes to the document that come out of the consensus-forming process.

## Updates after a document is "finished"

If for some reason an author does want to publish a new version of a
"finished" document, they will need to create a new draft with a new name.

Note to authors: (TODO: check on what happens to obsoleted I-Ds)

## Review process

Like all publications of Internet-Drafts, there is no review process before
publication other than mechanical nit checking.  The author uses
this mechanism at their own risk.

# Changes to "finished" drafts {#changes}

The following changes are made to an Internet-Draft when it is "finished":

## Naming {#naming}

The naming scheme for Internet-Drafts is usually `draft-*-[dd]`, where `[dd]`
is a zero-padded number with at least two digits.  A "finished" draft will
be published with a name in the form `draft-*-fin`.

## Expiry date

The finished output will not include an expiry date.  The expiry date would
otherwise occur:

* In the document header information
* At the bottom of each page of the text output
* In the "Status of this memo" section

## Boilerplate

The "Status of this memo" section usually contains the following paragraph:

```
  Internet-Drafts are draft documents valid for a maximum of six months and
  may be updated, replaced, or obsoleted by other documents at any time. It is
  inappropriate to use Internet-Drafts as reference material or to cite them
  other than as "work in progress."
```

This boilerplate may be replaced with a new paragraph that says:

```
  Internet-Drafts are draft documents do not represent the consensus of any
  community, but are the sole opinion of the authors. It is inappropriate to
  use Internet-Drafts as reference material or to cite them
  other than as "work in progress."
```

# Citation {#citation}

(Note: I don't know what to do with citations yet.  "Work In Progress" doesn't
seem quite right)

# Suggested workflow {#workflow}

Frequently authors will publish several versions of a document before declaring
it "finished".  Before marking an Internet-Draft as "finished", authors should
seek editorial review from wherever they can get it.  Before abandoning hope
of getting a document published through one of the Internet community's
other processes, the authors should have a conversation with a relevant Area
Director, working group chair, research group chair, or IAB member to consider
potential options.

# Required tooling changes {#tooling}

Several tools will need to be updated to support marking drafts as "finished".

## Draft generation tools

Tools such as xml2rfc will need to support the changes from {{changes}}.

## Internet-Draft submission tool

The tooling that accepts Internet-Draft submissions will need to be made aware
of "finished" drafts.  This tool may use the published file name as an
indicator that the author wants to publish a finished document.  Further
prompts may be added to ensure that the author has performed a full review,
that the author understands no further versions can be published, etc.

## Nit checking

The nit checker will need to know about "finished" drafts in order to check
the changes mentioned in {{changes}}.

## Citation library

The library of citation XML may need to have slightly different XML created
for "finished" drafts.

# Security Considerations {#security}

Authors of "finished" drafts, particularly those that deal with network
protocols, crypto streams, or other technical output, should consider the
consequences of security issues being found in their documents at a later
time.

# IANA Considerations

Drafts that are marked as "finished" are not different from other
Internet-Drafts with respect to registries that require "standards action"
or are "specification required".

--- back
