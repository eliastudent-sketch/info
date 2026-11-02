# Privacy Policy

**Effective date: November 2, 2026**

This Privacy Policy explains how the Discord bot operated under the public
name `buttercup_uwu` handles personal data. It covers the bot's commands,
games, moderation and message-report tools, update notifications, OAuth helper,
and local operational files. It does not cover Discord's own processing or
services operated by other providers.

The bot is free, is operated by an individual based in Sweden, and currently
runs on the operator's personal computer. It is available to users globally.
A separate Twitch bot is planned but is not running and does not currently
process Twitch data. This policy will be revised before Twitch features are
offered.

## 1. Who operates the bot and how to contact them

The operator and contact published for this service are:

- **Public operator name:** `buttercup_uwu`
- **Discord account:** [buttercup_uwu](https://discord.com/users/564486880763183111)
- **Support and privacy requests:** [Discord support server](https://discord.gg/uP8FVT3yaZ)

The operator is an individual based in Sweden and uses the public identity
above. No separate legal name, postal address, or email address is published in
this notice. This contact information does not determine whether additional
controller-identification details are legally required in a particular
situation.

The operator has not established that a Discord identity and support server
alone satisfy every identity or contact-information rule that may apply. No
legal name, geographical address, or privacy email is published here. If a
law applicable to a user's situation requires additional details or another
contact method, this notice does not claim that the current details satisfy
that requirement. The operator should obtain jurisdiction-specific advice and
publish any required details before continuing to offer the Service to users
covered by that rule.

## 2. Information the bot handles

The bot receives information through Discord when it is needed to provide a
feature. Depending on the feature, this can include:

- Discord user IDs, usernames, display names, and account-related details;
- server, channel, and role IDs and names, membership and permission context,
  member counts, and limited server snapshots;
- command text, arguments, URLs, game or poll choices, reminder details, and
  other information a user supplies to a feature;
- message and reaction identifiers, authors, timestamps, and metadata;
- moderation and blacklist IDs, reasons, audit records, and ban-export data;
- update-notification preferences and delivery status; and
- operational logs, health records, error details, and restart information.

The bot has a message-content intent to support commands and mention
statistics. The mention monitor records counts and up to 50 recent mention
events with user and server names or IDs; it does not intentionally retain the
full text of those monitored messages. Other commands, such as a user-invoked
message report, do process message text as described below.

### Suggestions

A suggestion can be stored with its text (up to 1,000 characters), the
submitter's Discord ID and username, the server ID when applicable, and the
submission time. The current bot code does not automatically expire these
records.

### Developer command audit records

The bot may append developer-command attempt records containing a timestamp,
user ID and username, command path, server ID, and interaction ID to a local
runtime log. The code does not set a time-based deletion period for that log.

### Update preferences and release messages

Users may choose update levels 0 through 6 in the public preference prompt or
with `/updates preference`. The bot stores preference and campaign status,
which may include user IDs, the selected level, conflict status, delivery
attempts, and Discord message/channel identifiers. The current campaign does
not DM members to ask them to opt in. Matching release notifications may be
sent by DM to users with a recorded preference; configured bot owners may
receive operational release messages regardless of preference. Old campaign
records do not all have automatic expiry.

### Member-submitted message reports

When a member selects **Apps → Report message**, the bot sends an embed
containing the selected message text (up to the embed's limit), a link to the
message, the reported author's and reporting member's Discord IDs, and server
and channel details. It sends the report to the private moderation channel
configured by that server's administrator and makes a separate best-effort DM
copy to each configured bot owner. The bot stores the configured destination
channel ID per server in a local runtime file. It does not create a separate
local archive of report contents. The report messages and DM copies are
retained and controlled by Discord and the receiving accounts/channels.

### Local developer telemetry

The bot stores aggregate daily command counts, outcomes, duration summaries,
error class names, and Discord rate-limit counts in a local SQLite database.
This telemetry is retained for a rolling 30 days and is available only to
configured bot owners through the developer metrics command or host access.
It does not contain command arguments, message content, user IDs, guild names,
or channel IDs, and is not sent to an external analytics service or AI
provider.

## 3. Why the information is used and intended legal bases

The bot uses information to respond to commands, run requested features,
enforce permissions, keep operational state after restarts, administer
moderation workflows, send opted-in update messages, deliver member reports,
prevent misuse, and diagnose errors or outages.

The operator's current, provisional GDPR legal-basis assessment, where the
GDPR applies, is:

- **Service features requested by a user or server administrator:** Article
  6(1)(b), to the extent processing is necessary to provide the requested
  feature under these Terms.
- **Optional release DMs:** Article 6(1)(a), consent represented by the user's
  affirmative update preference. A user can change or withdraw that preference
  through the prompt or `/updates preference`; withdrawal does not affect
  processing already carried out.
- **Security, abuse prevention, service reliability, and moderation reports:**
  Article 6(1)(f), the operator's intended legitimate interests in keeping the
  bot and participating communities operational and safer. This basis requires
  an appropriate necessity and balancing assessment; it does not apply where
  the individual's rights and interests override those interests.

The operator does not claim that every possible feature or deployment has been
independently assessed for lawful basis, and no complete legitimate-interests
assessment is represented here. IMY guidance says the controller must identify
and document the applicable basis before processing begins and inform people
about it. This notice does not itself establish a lawful basis or certify that
the provisional assessment is sufficient for every processing activity. The
operator must confirm and document the basis for each purpose before relying on
it, and review it before a feature's purpose or setup changes. Where a server
administrator uses a report or moderation information for the server's own
decisions, that administrator may have separate data-protection
responsibilities.

## 4. Where information is stored and how long it remains

The main bot currently runs on the operator's personal computer. Runtime data
is stored in local files or a local database under the bot's runtime directory.
The bot does not apply one expiry period to every record.

Known retention behavior includes:

- Developer telemetry: rolling 30 days.
- Main bot log: from version 1.0.2, rotates daily and retains up to 29 rotated
  files plus the active file (about 30 daily files). Rotation is triggered by
  the next log write after midnight using the host's local time; downtime can
  delay cleanup. Copies and backups outside the bot are not covered. Older
  size-based log backups created by versions before 1.0.2 are not automatically
  migrated or deleted by this change.
- Mention statistics: cumulative counts are held in memory during the process;
  up to 50 recent events and a local summary are written for the developer
  monitor. The in-memory counts start again after a process restart. The
  runtime file has no fixed time-based expiry.
- Suggestions, developer-command attempt records, update preferences and
  release-delivery records, blacklist data, moderation/export records, and
  other operational files: the current code does not set a general time-based
  deletion schedule. They may remain until overwritten or manually deleted.
- Message-report destination settings: retained locally per server until an
  administrator changes or disables them.
- Temporary public OAuth authorization state: expires after five minutes and
  can be used once. OAuth access tokens are handled in memory for the join
  request and are not saved by the helper.

Backups, Discord messages, owner DMs, and provider logs may persist beyond the
bot's own runtime files. The operator should review local data periodically and
delete information that is no longer needed, subject to security and legal
requirements.

## 5. Recipients and other services

The bot uses the Discord API. Discord receives API requests and processes
account, server, message, and interaction data under [Discord's Privacy
Policy](https://discord.com/privacy) and [Terms of
Service](https://discord.com/terms). Reports and update messages may be
delivered as described above to the selected Discord channel or user.

Other processing may occur when an optional feature is used:

- The music feature may request media metadata from YouTube using `yt-dlp`.
- The optional language-model feature connects to Ollama on the same
  computer (`localhost`); the bot's developer telemetry is not exported to an
  external AI service.
- If the separate user-join OAuth helper is run through a Cloudflare Quick
  Tunnel, Cloudflare proxies browser callback traffic to the operator's
  computer. The helper uses Discord's OAuth and API endpoints, handles the
  temporary access token and user ID in memory, and does not print the token,
  authorization code, state, user ID, or callback query string.
- The policy files are hosted in the public GitHub repository
  `eliastudent-sketch/info`. No GitHub Pages website is currently deployed.

These providers operate under their own terms and privacy practices. Their
processing may occur in countries other than the user's or operator's country.
The operator has not established a complete provider-by-provider map of
international transfer mechanisms; provider-specific details should be
checked in the relevant provider's privacy documentation.

The operator does not sell personal data and does not use a third-party
analytics service for developer telemetry.

## 6. Your privacy rights and requests

Where the GDPR applies, individuals may have rights to access, correct, erase,
restrict, or receive certain personal data, and to object to processing based
on legitimate interests. Where consent is the basis, it may be withdrawn at
any time. These rights are subject to the GDPR's conditions and exceptions.
You may also complain to the competent supervisory authority. In Sweden, that
authority is the [Swedish Authority for Privacy Protection
(IMY)](https://www.imy.se/).

To make a request, contact the operator through the private support/privacy
contact in the [Discord support server](https://discord.gg/uP8FVT3yaZ). Do not
post personal or sensitive information in a public channel. The operator may
ask for information reasonably needed to verify a request, and will respond
within the period required by applicable law. Some data is held by Discord,
server administrators, or other providers rather than in the bot's local
files; requests about those copies may need to be made to the relevant
provider or administrator.

## 7. Children

The bot does not request a date of birth or independently verify age, and it
does not have a separate bot-level age gate. Users must meet Discord's current
age requirements and any requirements that apply where they live.

Swedish law sets age 13 for a child's own consent only where an
information-society service is offered directly to that child and consent is
the legal basis; this is not a universal minimum age for every service or
processing purpose. The operator does not claim that this rule alone resolves
all age or children's-data obligations for a globally accessible bot.

## 8. Security

The operator restricts bot credentials, runtime files, and host access and
uses local storage and operational safeguards. No internet-connected service
can guarantee absolute security. Users and server administrators should avoid
sending highly sensitive information to the bot and should restrict access to
moderation channels and computers containing runtime data.

## 9. Geographic scope and legal limits

The bot is operated from Sweden and is technically available globally. That
does not mean every country's laws have been reviewed or that the bot is
certified for every jurisdiction. EU/EEA data protection requirements may
apply because of the operator's establishment; other countries' laws can
apply depending on their territorial rules, the service's activities, and
other facts. The operator has not completed a country-by-country applicability
analysis, a complete international-transfer assessment, or a full assessment
of each processing purpose's legal basis.

This notice is a description of known processing, not a promise that
publishing it alone makes the processing lawful. Where applicable law gives
you additional rights, those rights are not waived by this notice. If a
mandatory local requirement conflicts with this notice, the mandatory rule
controls. A public Discord contact may not meet a requirement for a legal
identity, postal address, email address, local representative, or other
contact information.

## 10. Changes and legal information

Material policy changes are published at the policy links and announced
publicly in the configured announcement channel. The bot does not send
policy-change DMs to members. A public announcement does not by itself
constitute consent where consent is legally required.

This notice is informed by the GDPR, Sweden's Data Protection Act, the
Swedish Electronic Commerce Act, and published guidance from IMY. It does not
certify compliance in every country or replace legal advice. The applicability
of the Electronic Commerce Act's provider-information duties to this free
service has not been determined. Relevant primary sources:

- [GDPR, Regulation (EU) 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- [Swedish Data Protection Act (2018:218)](https://www.riksdagen.se/sv/dokument-och-lagar/dokument/svensk-forfattningssamling/lag-2018218-med-kompletterande-bestammelser_sfs-2018-218/)
- [Swedish Electronic Commerce Act (2002:562)](https://www.riksdagen.se/sv/dokument-och-lagar/dokument/svensk-forfattningssamling/lag-2002562-om-elektronisk-handel-och-andra_sfs-2002-562/)
- [IMY: legal bases under GDPR](https://www.imy.se/verksamhet/dataskydd/det-har-galler-enligt-gdpr/rattslig-grund/)
- [IMY: data-subject rights](https://www.imy.se/verksamhet/dataskydd/det-har-galler-enligt-gdpr/de-registrerades-rattigheter/)
- [Discord Privacy Policy](https://discord.com/privacy)
