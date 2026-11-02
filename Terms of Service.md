# Terms of Service

**Effective date: November 2, 2026**

These Terms govern your use of the free Discord bot operated under the public
name `buttercup_uwu` (“Operator,” “we,” or “us”). The bot offers commands,
games, utilities, moderation-related features, reminders, update notifications,
and other functions made available through Discord (the “Service”).

**Operator contact:** [buttercup_uwu](https://discord.com/users/564486880763183111)
and the [Discord support server](https://discord.gg/uP8FVT3yaZ). The Operator
is an individual based in Sweden. No separate legal name, postal address, or
email address is published in these Terms.

The Service is currently free and is operated from the Operator's personal
computer. A separate Twitch bot is planned but is not part of the Service,
is not available under these Terms, and is not currently processing Twitch
data. If a Twitch service is launched, the applicable terms will be published
or updated before it is offered.

## 1. Agreement and scope

These Terms apply when you interact with the Service or use it in a server you
administer. If you use the Service for an organization or server, you confirm
that you are authorized to act for it. Server administrators may set additional
server rules, but those rules do not change these Terms or Discord's terms.

If you do not accept these Terms, do not use the Service and ask a server
administrator to remove or disable it. The Service's features and availability
may differ by bot version, server configuration, permissions, and host.

## 2. Eligibility and platform rules

You must be permitted to use Discord and the Service under Discord's current
age requirements and the laws applicable to you. The bot does not ask for your
date of birth or independently verify your age.

Your use of Discord remains subject to [Discord's Terms of
Service](https://discord.com/terms), [Community
Guidelines](https://discord.com/guidelines), and other applicable Discord
policies. When using Discord's developer platform, the Operator must also
comply with the [Discord Developer Terms](https://discord.com/developers/docs/policies-and-agreements/developer-terms-of-service)
and [Developer Policy](https://discord.com/developers/docs/policies-and-agreements/developer-policy).
Those agreements govern the relationship with Discord and are separate from
these Terms.

## 3. Using the Service

You may use the Service only for lawful purposes and in accordance with these
Terms and Discord's rules. You must not:

- use the Service to harass, threaten, defraud, or unlawfully target another
  person;
- attempt to access another person's account, private data, or server without
  authorization;
- interfere with the Service, evade rate limits or access controls, or use it
  to distribute malware or spam;
- use a command or moderation feature without the permissions or authority it
  requires; or
- use the Service in a way that violates applicable law or another person's
  rights.

The Service is not an emergency service and must not be relied on as the only
means of urgent communication, critical recordkeeping, or safety monitoring.

## 4. Server administrators and permissions

The server administrator decides whether to add the bot, which permissions to
grant, and which features to enable. Administrators are responsible for
configuring permissions and channels, controlling access to private moderation
channels, and ensuring their own use of the Service complies with Discord's
rules and applicable law.

Some features need Discord permissions, privileged intents, or access to a
specific channel. They may stop working if those permissions are removed or
changed. Grant only the permissions needed for the features you choose to use.
The Operator does not control server roles, channel visibility, or what
administrators do with information delivered to their server.

## 5. Moderation and message reports

The **Apps → Report message** context command lets a member submit a selected
message for review. The report includes message text and a link, the reported
author and reporter identifiers, and server/channel context. It is sent to the
private report channel configured by a server administrator and copied to the
configured bot owners by Discord DM. Reports are best-effort; the bot cannot
guarantee delivery or that a recipient will review or act on one.

An administrator can configure or disable the report destination using
`/manage admin report-channel`. Administrators should restrict the channel to
moderators who need access. Do not submit a report unless you are comfortable
sharing the selected message with those recipients. Do not use the feature for
emergencies; contact the relevant server moderators or authorities directly.

Other moderation commands may affect a member's access to a server or bot.
Those actions are subject to the permissions of the person invoking the
command and Discord's audit and moderation systems. The Operator does not
guarantee that a moderation action is correct or reversible.

## 6. Update preferences and messages

The bot may publish a public update-preference prompt. Users may choose levels
0 through 6 or change their preference using `/updates preference`. The bot
does not enumerate all members or send DMs asking them to opt in. Release
messages may be sent by DM to users whose saved preference matches the release;
configured bot owners may also receive operational release messages.

Discord may block or delay messages, and the Operator cannot guarantee
delivery or that a user has read a message. Policy changes are announced
publicly in the configured channel and published at the policy links. The bot
does not send policy-change DMs to members. A public announcement does not
replace consent or another notice where the law requires it.

## 7. User content

You retain rights you hold in content you submit. You authorize the Operator
to receive, process, and transmit that content only as reasonably necessary
to provide the feature you requested, operate the Service, maintain security,
and comply with law. For example, a message report is shared with its
configured recipients as described above. Discord and other providers may
process content under their own terms and policies.

Do not submit content you are not entitled to share, or content that is
unlawful, abusive, or malicious. The Operator does not claim ownership of your
content.

## 8. Privacy

The [Privacy Policy](./Privacy%20Policy.md) explains what information the bot
handles, its purposes and intended legal bases, storage and known retention,
recipients, and how to make a privacy request. Discord separately processes
data under Discord's own policies.

The bot stores some information in local runtime files on the Operator's
computer. Not all records have automatic deletion periods. The Privacy Policy
describes the specific retention behavior the current code establishes.

## 9. Intellectual property

The Operator retains rights in the bot software, branding, and materials,
subject to third-party rights and licenses. The source code is not offered
under a public software license; these Terms do not grant permission to copy,
redistribute, sell, or modify it. This does not restrict rights that applicable
law or a third-party license grants.

Discord, Twitch, YouTube, and other third-party names and services belong to
their respective owners. No affiliation or endorsement is implied. Twitch is
mentioned only as a planned, separate service and is not included in the
current Service.

## 10. Third-party services

The Service depends on Discord and may use third-party libraries or optional
services, such as YouTube for media metadata, Ollama running locally for an
optional language-model feature, or Cloudflare Tunnel for an optional OAuth
helper. Those providers have separate terms, privacy practices, security
controls, and availability. Your use of a provider's service is also governed
by its terms.

The optional user-join OAuth helper asks a consenting user to authorize
`identify` and `guilds.join`, then asks Discord to add that user to the
configured server. It is not required to use the main bot. Its temporary
authorization state expires after five minutes and is single-use; the helper
handles an access token in memory and does not save it.

## 11. Availability, changes, and termination

The Service is provided over the internet and may be interrupted by
maintenance, computer or network outages, Discord or provider outages, rate
limits, software defects, or changes to Discord's APIs. The Operator may add,
change, suspend, or discontinue a feature, or suspend access where reasonably
needed for security, abuse prevention, legal compliance, Discord requirements,
or maintenance.

You may stop using the Service at any time. A server administrator may remove
or disable it. The Operator may suspend or end the Service without guaranteeing
that all runtime data can be recovered or immediately removed. Data handling
after removal is described in the Privacy Policy.

## 12. Disclaimers

The Service is provided without a promise of uninterrupted availability or
that it will be error-free or meet a particular need. To the extent permitted
by law, the Operator disclaims implied warranties that may otherwise apply to
a free service. Nothing in these Terms excludes a warranty, remedy, or right
that cannot lawfully be excluded or limited.

## 13. Liability

Nothing in these Terms limits liability where a limitation is prohibited by
applicable law, including mandatory consumer protections. To the extent
permitted by law, the Operator is not responsible for indirect or consequential
losses that could not reasonably be expected from use of a free, non-critical
Discord bot, or for acts of Discord, server administrators, or other
independent providers. This section does not limit responsibility for the
Operator's own conduct where the law does not permit that limitation.

## 14. Governing law and disputes

Swedish law governs these Terms, without displacing mandatory consumer
protections or rules that require another law or forum to apply. A consumer
may retain any mandatory right to bring a claim before a court or authority
available under the law that applies to that consumer. Nothing here requires
arbitration or waives a right that cannot legally be waived.

If you have a concern, contact the Operator using the support channel below
before bringing a non-urgent dispute. This does not prevent you from contacting
a regulator or exercising a legal right.

## 15. Changes and general terms

The Operator may revise these Terms to reflect changes to the Service or law.
The effective date will be updated for material changes, which will be
published at the policy links and announced publicly in the configured
announcement channel. Continued use is not treated as consent where applicable
law requires a different form of notice or agreement. If you do not agree to
a change, stop using the Service and ask a server administrator to remove it.

If a provision is unenforceable, it will be applied only to the extent allowed
by law; the remaining provisions continue to apply. A failure to enforce a
provision is not a waiver of it.

## 16. Contact

For service questions, contact the Operator through the [Discord support
server](https://discord.gg/uP8FVT3yaZ) or the [public Discord
account](https://discord.com/users/564486880763183111). Do not post passwords,
tokens, or highly sensitive personal information in public channels.

These Terms reflect the current free Discord bot and its published features.
They are based on the cited platform materials and Swedish/EU legal sources;
they are not a legal opinion or a certification of compliance in every
jurisdiction.

### Official references

- [Discord Terms of Service](https://discord.com/terms)
- [Discord Developer Terms of Service](https://discord.com/developers/docs/policies-and-agreements/developer-terms-of-service)
- [Discord Developer Policy](https://discord.com/developers/docs/policies-and-agreements/developer-policy)
- [Swedish Distance Contracts Act (2005:59)](https://www.riksdagen.se/sv/dokument-och-lagar/dokument/svensk-forfattningssamling/lag-2005-59-om-distansavtal-och-avtal-utanfor_sfs-2005-59/)
- [Swedish Data Protection Act (2018:218)](https://www.riksdagen.se/sv/dokument-och-lagar/dokument/svensk-forfattningssamling/lag-2018218-med-kompletterande-bestammelser_sfs-2018-218/)
- [GDPR, Regulation (EU) 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
