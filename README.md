# Zero Trust: From Buzzword to Action

**Workplace Ninja Summit 2026** · Pouyan Khabazi, Cloud Security MVP

Last year at this event we ran a live attack: one phish, and by the end we owned every Azure
subscription in the tenant. The question I got afterwards, every time, was the same one:
*okay, so how do I actually stop it?*

This session is that answer. Same attack, walked backwards, one Zero Trust control at a time.
Eight steps, six pillars, and the exact setting that made each step possible. Not one of those
steps needed a zero-day.

## What's here

| File | What it is |
|---|---|
| [`action-pack.pdf`](action-pack.pdf) | The take-home, print-ready |
| [`action-pack.md`](action-pack.md) | Same thing, readable right here on your phone |

Both carry the per-pillar action list: what to configure, the licence tier it needs, who owns
it, what to switch **off**, plus the two detection queries and the ownership sign-off row.

**Slides go up right after the session.**

## Start here

If you take one thing away, take this: **measure before you change.**

```powershell
Install-Module ZeroTrustAssessment -Scope CurrentUser
Connect-ZtAssessment
Invoke-ZtAssessment
```

Read-only. It grades every pillar and writes a scored HTML report. Large tenants can take
over 24 hours, so run it and walk away. Subsequent runs need Global Reader, Security Reader,
Exchange Administrator and SharePoint Administrator.

Then read three things in the report, in this order: your score per pillar (where are you
weakest), the high-risk failed checks at the top (start there, not at the bottom), and the
Identity tab (that is the pillar this whole attack lived in).

## Then do these five, in order

1. Phishing-resistant MFA for admins
2. PIM for Global Admin, and kill standing GA
3. Key Vault off the public network, rotate or remove secrets
4. The free Azure Monitor alert on the elevate-access action
5. Windows LAPS + Credential Guard + the three ASR rules

Every one of those is doable this week with licences you already own. Four of the five cost
nothing extra.

## And then the hard part

Write a name next to each pillar. Not a team, a person. The reason most tenants have
half-built Zero Trust is not the tooling, it is that nobody owns each pillar, so each one is
sixty percent done and no one is accountable for the other forty. The sign-off row is in the
action pack.

Unowned Zero Trust is not Zero Trust. It is a slide deck.

## Resources

- [Microsoft Zero Trust Assessment](https://github.com/microsoft/zerotrustassessment) (part of the Zero Trust Workshop)
- [Live demo of the scored report](https://aka.ms/ZeroTrust/Demo)
- [Microsoft Cybersecurity Reference Architectures (MCRA)](https://aka.ms/MCRA)

## Contact

Pouyan@cofend.io · [@pkhabazi](https://www.linkedin.com/in/pkhabazi/)

---

*Zero Trust does not mean no trust. It means no assumptions.*
