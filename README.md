# Phishing Email Checker

A small Python tool that reads an email's text and flags things that
commonly signal phishing: urgent pressure language, a brand name
mentioned alongside links that don't go to that brand's real domain,
and lookalike domains.

This is a learning tool, not a spam filter. It checks text you paste
in, it doesn't connect to any inbox.

## What it does

- Flags common pressure phrases ("verify your account", "act now",
  "your account will be suspended")
- Compares brand names mentioned in the email against the domains
  actually linked in it
- Flags domains that look like near-misses of a real brand's domain
- Flags links where the visible text and the real destination don't match

## How to run it

    python3 phishing_checker.py

Paste the email's text (or its raw HTML, for link checks), then press
Ctrl+D (Mac/Linux) or Ctrl+Z then Enter (Windows).

## Example

Input:

    Your PayPal account will be suspended. Please verify your account.
    <a href="https://paypa1-secure.com/login">paypal.com login</a>

Output:

    2 possible issue(s) found:
      - Pressure language found: "verify your account"
      - Mentions "paypal" but links point to paypa1-secure.com, not paypal.com.

## Why I built it

Part of a series of small security projects on Cipherora
(cipherora.com), where I write up what I built, what broke, and what
I learned.
