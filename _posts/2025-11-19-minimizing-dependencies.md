---
title: "An Independent Security Audit of Bitcoin Core"
permalink: /blog/2025/11/19/bitcoin-core-security-audit/
layout: post
author: brink
name: "brink"
alt: An Independent Security Audit of Bitcoin Core
category: "technical"
description: As part of Brink's mission to ensure the safety and robustness of the open-source Bitcoin Core software, we recently sponsored an independent security audit of the Bitcoin Core codebase.
---

At Brink, our mission is to ensure that Bitcoin continues to be the world’s most
secure, reliable, and resilient monetary network. As part of this mission and to
ensure the safety and robustness of the open-source Bitcoin Core software that
powers the network, **Brink recently sponsored an independent security audit of
the Bitcoin Core codebase**.

The assessment was conducted by [Quarkslab][], a respected software security
firm, and was coordinated with the help of the [Open Source Technology
Improvement Fund (OSTIF)][ostif]. Funding was provided by Brink through the
generous support of our donors. Technical collaboration came from both Brink
(Niklas Gögge) and Chaincode Labs (Antoine Poinsot) engineers.

This work represents the first public, third-party audit of Bitcoin Core.

The full report is publicly available here: [Quarkslab Bitcoin Core Technical
Security Audit Report][ostif report]

## Why we funded this work

As the reference implementation that powers the Bitcoin network, Bitcoin Core
helps secure trillions of dollars in value. The more security-minded eyes, with
different perspectives, on the codebase, the better.

Despite a strong security track record, the project had never undergone an
external security assessment. Brink helped initiate this engagement to provide
an additional layer of assurance for developers, node operators, holders, and
businesses who rely on Bitcoin Core.

To be clear, the goal wasn’t to earn Bitcoin Core a stamp of approval or a
certification badge. The goal was to actively search for vulnerabilities,
improve testing methodologies, and identify practical ways to strengthen the
codebase.

## What was done

Over a four-month period (May - September 2025), for a total of 100 man days,
Quarkslab’s researchers performed a technical review of Bitcoin Core. Their
focus was on the most security-critical components of the software, including
the peer-to-peer networking layer, mempool, chain management, and consensus
logic.

Quarkslab engineers initially spent a week in Brink’s London office to get
familiar with Bitcoin Core’s architecture and codebase before pursuing the
manual code review and testing that went into the audit.

The audit combined:

- **Manual code review** of complex areas like thread handling and transaction
  validation
- **Static and dynamic analysis**, using tools integrated into Bitcoin’s CI
  workflows
- **Advanced fuzz testing**, expanding on the work already maintained by Bitcoin
  Core contributors

Three  Quarkslab security engineers contributed to the effort over the duration
of the project.

Quarkslab also encouraged Bitcoin Core’s newer approaches to testing, such as
structured and differential fuzzing and the [fuzzamoto][fuzzamoto gh] and
[bitcoinfuzz][bitcoinfuzz gh] initiatives, to improve future coverage and
reliability.

## What they found

The auditors reported **no critical, high, or medium-severity issues**. They
identified **two low-severity findings** and **thirteen informational
recommendations**, none with security impact according to [Bitcoin Core’s
vulnerability classifications][bc advisories].

The engagement also produced improvements to Bitcoin Core’s testing
infrastructure:

- New fuzzing harnesses for block connection and chain reorganization, reaching
  code paths never exercised before
- A virtual filesystem utility to make fuzzing faster and more effective
- New fuzzing corpus
- New utilities for regression testing
- Targeted suggestions to improve thread-safety annotations and code readability

Some of these contributions are being prepared for upstream review and
integration into the main Bitcoin Core repository.

## Continuing the mission

The results confirm what long-time contributors and users already know: Bitcoin
Core is a mature, conservatively engineered, and exceptionally well-tested
codebase. Independent review strengthens that confidence.

Thank you to Quarkslab, the OSTIF, Niklas and Antoine for their work on this
audit project. Engaging third party security firms could be valuable again in
the future for targeted review of specific new components proposed for Bitcoin
Core.

Brink exists to ensure Bitcoin’s open-source infrastructure remains strong for
decades to come. Funding independent reviews like this is one part of that
mission. We’ll continue supporting the people and projects that make sure
Bitcoin doesn’t break.

## About Brink

Brink is a Bitcoin research and development centre, founded in 2020 to support
independent open source protocol developers and mentor new contributors. If you
or your organization is interested in supporting open source Bitcoin
development, feel free to email us, [donate@brink.dev][donate].

Developers interested in the grant [program][programs] can apply now.

[QuarksLab]: https://www.quarkslab.com/
[ostif]: https://ostif.org/
[ostif report]: https://ostif.org/wp-content/uploads/2025/11/25-05-2133-REP-bitcoincore-security-assessment-V1.3.pdf
[fuzzamoto gh]: https://github.com/dergoegge/fuzzamoto
[bitcoinfuzz gh]: https://github.com/bitcoinfuzz/bitcoinfuzz
[bc advisories]: https://bitcoincore.org/en/security-advisories/
[donate]: mailto:donate@brink.dev
[programs]: /programs
