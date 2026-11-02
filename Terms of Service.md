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
or updated before it is offered. These Terms describe Discord bot version
1.0.2 as of November 2, 2026.

## 1. Agreement and scope

These Terms apply when you interact with the Service or use it in a server you
administer. If you use the Service for an organization or server, you confirm
that you are authorized to act for it. Server administrators may set additional
server rules, but those rules do not change these Terms or Discord's terms.

If you do not accept these Terms, do not use the Service and ask a server
administrator to remove or disable it. The Service's features and availability
may differ by bot version, server configuration, permissions, and host.

The Service is a collection of optional Discord bot features, not a single
guaranteed package. Depending on the bot version and server configuration it
may include games (including turn-based games), polls, reminders, text and
calculation utilities, music/media metadata lookup, member and server
information, suggestions, update preferences, owner-only diagnostics, and
administrator/owner moderation tools. Some actions occur only in response to
a user's command; some background tasks maintain service health or complete
an explicitly approved release. The bot does not promise that every command
will be enabled or available in every server.

Some interactive state is temporary. Polls, games, reminders, AI conversation
history, and music queues are not all stored durably. A restart can cancel a
pending reminder and discard an active game, queue, or local AI history.
Discord messages already posted for those features may remain even after the
bot's in-memory state is gone.

These Terms apply to the Discord service only. They do not govern Discord's
own platform, a server administrator's separate rules, an optional provider's
service, or a future Twitch bot. Each of those may be governed by separate
terms.

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

You are responsible for keeping your Discord account secure and for activity
carried out through your account. The Operator does not control Discord's
account eligibility checks, age checks, enforcement decisions, or appeal
processes. If Discord suspends an account or changes an API, the bot may be
unable to serve that account or server.

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

You are responsible for checking a command's target, options, and any
confirmation prompt before submitting it. A command may publish a response in
a server channel or send a private message, depending on how that feature is
designed. Do not include passwords, payment-card information, authentication
codes, government identifiers, health information, or other highly sensitive
details in a command, suggestion, poll, reminder, or report unless the
specific feature expressly requires and is appropriate for that information.

Commands may create public or server-visible messages. In particular, `/poll`
posts its question, options, and vote totals in Discord; a reminder is sent by
DM when its timer completes; and `/ai talk` responds in the server channel.
Do not treat a command or response as confidential merely because it was
submitted as an interaction.

You must not use the Service to:

- send unsolicited or bulk messages, evade Discord rate limits, or automate
  user accounts in a way Discord prohibits;
- probe, disrupt, overload, reverse engineer, or bypass security controls of
  the bot, Discord, or another provider;
- impersonate another person, submit a knowingly false report, or use
  moderation tools to retaliate, discriminate, or harass;
- upload or transmit content that infringes another person's rights or
  violates privacy, confidentiality, data-protection, or other applicable
  law; or
- use the bot as a substitute for professional, legal, medical, financial,
  emergency, or safety advice.

These restrictions do not give the Operator a right to inspect every
conversation or to guarantee that all misuse will be detected. They describe
conditions of use; enforcement depends on information available to the
Operator, Discord, and server administrators.

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

By adding the bot or enabling a feature, an administrator represents that
they have authority to do so and to grant the permissions and intents they
select. Administrators should tell members when a feature processes or sends
their information, limit access to moderation and export channels, use the
least permissions that allow the chosen feature to work, and remove access
when no longer needed. Administrators remain responsible for their own
moderation decisions and for information they export, copy, or retain.

Ban export files contain Discord account IDs and are written as ordinary
local text files; the combined export also contains server IDs. Authorized
administrators and owners must protect these files, use them only for a
legitimate moderation purpose, and avoid sharing them with people who do not
need access. Ban imports can cause moderation actions. Verify the source,
server, IDs, and any supplied reasons before importing; the Operator does not
endorse or guarantee the accuracy of an imported list.

The Operator may change default permissions or disable a feature to address
security, platform-policy, legal, or reliability concerns. No administrator
is promised a particular command, intent, or permission will remain available.

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

Reports are allegations for human review, not findings that a rule was
violated. The Operator does not independently investigate every report, decide
whether reported content is true, or guarantee action by a server's moderators.
The server administrator controls who can read the configured report channel
and is responsible for making that channel private and handling its contents.
Configured bot owners can receive a separate copy by DM to help operate and
moderate the bot. Discord may retain those messages under its own systems and
policies.

Use the report command only for a good-faith concern about the selected
message. Include only information relevant to review. Do not use it to
distribute unlawful content, expose private information unrelated to the
report, threaten another member, or create knowingly false reports. If a
message creates immediate danger, contact appropriate emergency services or
the responsible platform moderators instead of relying on this command.

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

Update preference levels describe the kinds of release announcements a user
has chosen to receive; they are not a promise of a particular number or
frequency of messages. Level 0 means no subscriber release notifications.
Levels 1-6 correspond to the available update categories. A user can change
their preference through `/updates preference`. The bot checks the saved
preference when building and sending an approved release, but delivery can
still fail because of Discord settings, blocked DMs, removed accounts, or
technical problems.

Each release requires a configured owner to prepare and explicitly approve
the release after reviewing its content and recipient preview. Configured bot
owners may receive operational release messages regardless of subscriber
preferences, including level 0. Approved release text is also posted in the
configured public announcement channel. The bot records delivery states to
avoid duplicate subscriber messages and to allow incomplete approved releases
to resume after a restart. Those records can contain recipient identifiers
and message identifiers, as explained in the Privacy Policy.

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

You are responsible for deciding whether you have the right to submit content
and whether it contains another person's personal, confidential, or sensitive
information. A report authorizes the bot to forward the selected message only
to the configured moderation channel and configured bot owners as described
above; a suggestion is stored locally for operator review. Submission does
not make the Operator the owner of the content and does not authorize public
redistribution or unrelated use.

You grant the Operator a limited, non-exclusive, revocable permission to
receive, store temporarily or persistently as the feature requires, reproduce
in a report, and transmit the submitted content solely to deliver the
requested feature, maintain the Service, handle security or abuse, or comply
with law. This permission ends when the relevant processing purpose ends,
subject to copies already delivered through Discord and any lawful retention.
This clause does not transfer your ownership or grant a license to use your
content for advertising, model training, or unrelated publication.

## 8. Privacy

The [Privacy Policy](./Privacy%20Policy.md) explains what information the bot
handles, its purposes and intended legal bases, storage and known retention,
recipients, and how to make a privacy request. Discord separately processes
data under Discord's own policies.

The bot stores some information in local runtime files on the Operator's
computer. Not all records have automatic deletion periods. The Privacy Policy
describes the specific retention behavior the current code establishes.

The bot does not promise that deleting a message in Discord, leaving a server,
revoking a permission, uninstalling the bot, or changing an update preference
will erase copies already retained by the Operator, Discord, a moderator, or a
message recipient. Requests about the Operator's local records may be sent
through the support/privacy route described in the Privacy Policy and will be
handled under applicable law.

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

Use of the OAuth helper is optional. Before authorizing, review the Discord
consent screen and proceed only if you want to authorize the stated scopes.
The helper does not promise that Discord will accept the request or that the
user will remain in the server. You can revoke an application's authorization
using Discord's account settings; removal from a server may need to be done
separately. Do not send an OAuth authorization code or access token to the
Operator or another person.

The music/media utility may retrieve public metadata from a third-party
platform or tool. It does not grant rights to download, copy, or redistribute
protected material. You are responsible for complying with the platform's
terms, copyright rules, and any restrictions that apply to the requested
content. Media availability, accuracy, and playback are not guaranteed.

If a local language-model utility is enabled, it connects to an Ollama
instance on the Operator's computer at `localhost`. The current `/ai talk`
implementation sends the latest prompt to that local endpoint, stores prompt
and reply pairs in process memory associated with the user's account, and
does not send the stored history as model context. A restart clears that
in-memory history. Do not submit confidential or sensitive information. A
separately configured Ollama model or proxy may have its own processing
behavior, which is not established by the bot code. The bot's aggregate
developer telemetry is not exported to an external AI service, but that
statement does not change any processing by Discord or another provider used
by an individual feature.

The standard Windows launchers enable the local VRChat OSC sender by default.
It sends compact, aggregate bot status, network, and seven-day command-health
values to the local VRChat OSC chatbox receiver; it does not send account
IDs, server names, mention-monitor details, or custom activity text. The text
may be visible through VRChat's chatbox features. You can disable the sender
by setting `BOT_ENABLE_VRC_OSC=0`. VRChat controls its own handling and
display of OSC chatbox messages.

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

The Operator may suspend a user or feature where reasonably necessary to
protect the Service, users, Discord platform, or a third party; respond to
credible abuse; follow a legal requirement or Discord direction; investigate
a security incident; or prevent material operational harm. Where reasonably
possible and lawful, the Operator may provide an explanation through Discord.
The Operator is not required to give advance notice where doing so would
create a security, abuse, or legal risk. You may stop using the Service and
ask a server administrator to remove it; that does not automatically erase
historical data or messages outside the Operator's control.

The bot may require updates to maintain compatibility or security. A change
may alter commands, permissions, or feature behavior. The Operator will make
reasonable efforts to announce material changes publicly but cannot guarantee
that every user sees or reads an announcement. If a legal rule requires a
specific notice or affirmative agreement, these Terms do not replace it.

## 12. Disclaimers

The Service is provided without a promise of uninterrupted availability or
that it will be error-free or meet a particular need. To the extent permitted
by law, the Operator disclaims implied warranties that may otherwise apply to
a free service. Nothing in these Terms excludes a warranty, remedy, or right
that cannot lawfully be excluded or limited.

The bot's responses, game outcomes, server data, member counts, media
metadata, and diagnostic values may be incomplete, delayed, stale, or
incorrect. They are provided for convenience and are not an authoritative
record. Server administrators should verify information before using it for
important moderation, account, or safety decisions. The Operator does not
warrant that a third-party API, Discord permission, internet connection, host
computer, or local runtime file will remain available or preserve data.

The bot does not guarantee delivery of a reminder, a successful Discord DM,
continuous music playback, recovery of an active poll/game/queue after
restart, or completion of an import/export operation. Local bot health and
telemetry shown through VRChat OSC are snapshots, not a real-time monitoring
or incident-response service.

## 13. Liability

Nothing in these Terms limits liability where a limitation is prohibited by
applicable law, including mandatory consumer protections. To the extent
permitted by law, the Operator is not responsible for indirect or consequential
losses that could not reasonably be expected from use of a free, non-critical
Discord bot, or for acts of Discord, server administrators, or other
independent providers. This section does not limit responsibility for the
Operator's own conduct where the law does not permit that limitation.

Nothing in this section excludes or limits liability for intentional
misconduct, fraud, gross negligence where it cannot be excluded, death or
personal injury where limitation is prohibited, a breach of a non-waivable
statutory duty, or any consumer remedy that applicable law preserves. If you
are a consumer, the mandatory rules of your country of residence continue to
apply where the law so provides. The Service is free and the Operator does not
promise compensation for interruption, lost game state, deleted runtime
records, or actions taken by independent Discord server administrators,
except to the extent such a limitation is unlawful.

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

## 16. Free service and no purchase obligation

The Service is currently offered without a subscription price or in-bot
purchase. The Operator does not require users to provide personal information
as payment for access. Discord necessarily provides account and service data
when a person uses Discord, and the bot processes limited information to
operate requested features; this is described in the Privacy Policy. The
Operator does not represent that this data processing is legally equivalent
to a fee or that a user waives privacy rights by using a free feature.

The Operator may decide to introduce optional paid features or another
commercial arrangement in the future only after publishing applicable terms,
pricing, required consumer information, and privacy disclosures before that
offer is made. Nothing in these Terms authorizes a charge or creates a payment
obligation now.

## 17. User content and permission to process

You retain ownership of content and rights you had before submitting it.
These Terms do not transfer ownership to the Operator. You remain responsible
for ensuring you have permission to submit the content and that your
submission does not violate a law, confidentiality obligation, or another
person's rights.

To operate a feature you request, you grant the Operator a limited,
non-exclusive permission to receive, process, store as described in the
Privacy Policy, and transmit the content to the feature's intended
destination. For example, the message-report feature sends the selected
message to a configured moderation channel and copies it to configured bot
owners; a suggestion is stored locally for operator review. The permission is
limited to providing, securing, and supporting that feature and complying
with law. It does not authorize advertising, sale, public redistribution, or
training an external AI model on your content.

Discord and other providers may separately process or retain content under
their own terms. A moderator or other recipient who receives a copy may also
make a separate copy. The Operator cannot revoke those copies through these
Terms.

## 18. Reports, moderation, and complaints

The report command is a routing tool, not an emergency line, investigation
service, or promise of enforcement. The reporter's selection and description
may be incomplete, and the reported person may not be notified by the bot.
The bot sends the report to the destination configured by the server
administrator and attempts an owner DM copy. The bot does not guarantee that
either destination is available or that a moderator reads or acts on the
report.

Questions or concerns about a report can be sent privately to the Operator
through the support server. A person may also contact the server
administrator, Discord, or a competent authority as appropriate. Do not use
the report workflow to submit threats, emergencies, knowingly false claims,
or personal information unrelated to the issue. The Operator may decline to
forward a report if the destination is missing, inaccessible, or unsafe.

## 19. Privacy requests and data deletion

The Privacy Policy describes the information handled, local retention, and
how to make a request. A request to access, correct, erase, restrict, object
to, or receive information will be handled under the law that applies. The
Operator may verify the requester's identity proportionately and may retain
limited information where a legal exception or another person's rights
require it.

Removing the bot from a server, deleting a Discord message, leaving a server,
or changing a preference does not necessarily remove local runtime records,
Discord copies, moderator copies, exports, or backups. The Operator will not
promise instant or universal deletion of information the Operator does not
control. A request can be sent using the support route in the Privacy Policy;
do not include account credentials or authentication secrets.

## 20. Service operation and technical limits

The Service may rely on the Operator's personal computer, local files,
internet connection, Discord's API, and optional providers. Any of these can
fail or change. Commands can time out, deliver duplicate or delayed responses,
or become unavailable when Discord imposes a rate limit or permission change.
Game, poll, reminder, or release state can be lost or become inconsistent
after a crash, deployment, corrupted file, or provider outage.

The Operator may perform maintenance, change configuration, deploy a new
version, or temporarily disable a feature without guaranteeing advance notice
for every maintenance event. The bot is not a backup system. Do not rely on
it as the only copy of a ban list, message, reminder, poll, game, or other
record that matters to you.

## 21. Consumer rights and mandatory law

These Terms do not take away rights that cannot be waived under applicable
consumer, privacy, accessibility, or other mandatory law. If a term conflicts
with a mandatory rule that applies to a user, the mandatory rule prevails to
the extent of the conflict and the remaining terms continue where possible.
The Operator does not claim that a Swedish governing-law clause can displace
mandatory protections or jurisdiction rules that apply to a consumer
elsewhere.

The Service is currently free and operated by an individual in Sweden. The
Operator has not determined whether every consumer-information or
distance-contract rule applies to this arrangement. If the Service's funding,
pricing, data-for-service arrangement, or commercial status changes, these
Terms and required pre-contract information must be reviewed before that
change is offered.

## 22. No agency, partnership, or endorsement

These Terms do not create an employment relationship, agency, partnership,
joint venture, or fiduciary relationship between a user and the Operator or
between the Operator and a server administrator. A server administrator
cannot bind the Operator or change these Terms on the Operator's behalf.
Discord and other named providers are independent services; their appearance
in these Terms does not mean they sponsor, endorse, or control the bot.

## 23. Contact

For service questions, contact the Operator through the [Discord support
server](https://discord.gg/uP8FVT3yaZ) or the [public Discord
account](https://discord.com/users/564486880763183111). Do not post passwords,
tokens, or highly sensitive personal information in public channels.

The Operator has not established that these Discord contact routes satisfy
every applicable legal requirement for identifying a service provider or
controller. No separate legal name, geographical address, or privacy email is
published. If applicable law requires those details or a different notice,
these Terms do not claim that the current contact information is sufficient.
The Operator should obtain jurisdiction-specific advice and publish any
required information before continuing to offer the Service to affected users.

These Terms describe the current free Discord bot and its published features.
They are based on the cited platform materials and Swedish/EU legal sources;
they are not a legal opinion or a certification of compliance in every
jurisdiction. Laws outside Sweden may apply based on their own territorial
rules, and mandatory rights are not waived by choosing Swedish law.

### Official references

- [Discord Terms of Service](https://discord.com/terms)
- [Discord Developer Terms of Service](https://discord.com/developers/docs/policies-and-agreements/developer-terms-of-service)
- [Discord Developer Policy](https://discord.com/developers/docs/policies-and-agreements/developer-policy)
- [Swedish Distance Contracts Act (2005:59)](https://www.riksdagen.se/sv/dokument-och-lagar/dokument/svensk-forfattningssamling/lag-2005-59-om-distansavtal-och-avtal-utanfor_sfs-2005-59/)
- [Swedish Electronic Commerce Act (2002:562)](https://www.riksdagen.se/sv/dokument-och-lagar/dokument/svensk-forfattningssamling/lag-2002562-om-elektronisk-handel-och-andra_sfs-2002-562/)
- [Swedish Data Protection Act (2018:218)](https://www.riksdagen.se/sv/dokument-och-lagar/dokument/svensk-forfattningssamling/lag-2018218-med-kompletterande-bestammelser_sfs-2018-218/)
- [GDPR, Regulation (EU) 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
