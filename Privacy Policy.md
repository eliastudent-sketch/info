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

### Information by feature

The following describes the main processing paths in the current Discord bot.
Not every item is collected from every user, and the bot does not use every
feature in every server.

| Feature | Information handled | What the bot does with it |
|---|---|---|
| Slash commands and components | Discord account and interaction identifiers, command name, selected options, interaction time, server/channel context, and information needed to reply | Checks the request and permissions, runs the requested operation, and sends a response through Discord |
| Prefix commands | Message identifier, author, message text needed to recognize the configured prefix and command, and server/channel context | Parses the command and runs permitted local developer or help actions; the bot does not intentionally store every ordinary message |
| Games, polls, and interactive views | Player IDs, choices, scores, board/card state, poll options and votes, component interaction identifiers, and sometimes message identifiers | Keeps active game state in process memory; poll views time out after 24 hours and Tic-Tac-Toe views after 15 minutes; Discord messages may remain after the in-memory state ends |
| Reminders and user-requested utilities | Reminder text, delay, and requester identity needed to schedule and attempt delivery | `/remind` accepts delays from 1 second to 7 days and holds its task in process memory; it sends the supplied text to the requester's Discord DM when due |
| Music and media | YouTube URL, retrieved title/stream metadata, queue/current-track state, server and voice-channel context, and the requester's display name | Retrieves track metadata without downloading the media file, maintains a per-server in-memory queue, and streams audio through Discord voice |
| Local AI feature | User prompt and generated reply, the Discord user ID used to associate in-memory conversation state, and the selected local model | Sends the latest prompt to the Ollama HTTP endpoint on the bot computer and stores prompt/reply pairs in process memory; accumulated history is not sent as context |
| Server and member utilities | Server, channel, role, member, owner, and permission information returned by Discord | Produces the response requested by the user or administrator; local snapshots include bot/server names and IDs, counts, owner IDs, status, latency, and ban-export run count |
| Mention monitoring | Mention author/target account IDs and names in cumulative local counters; up to 50 recent mention entries include display names, server name, bot flags, targets, and timestamps | Updates the local developer monitor when a message has mentions; it does not intentionally archive the full text of those messages |
| Suggestions | Suggestion text (maximum 1,000 characters), submitter ID/name, server ID where applicable, submission time, and generated suggestion identifier | Saves the submission to the local suggestions file for the operator to review |
| Apps message reports | Selected message text (truncated to Discord embed limits), message link and ID, author and reporter IDs/names, timestamp, server and channel identifiers/names | Sends the report to the server's administrator-configured report channel and attempts a separate DM to configured bot owners |
| Update preferences | User ID, level 0-6, choice source, status, timestamps, conflict information, and delivery/campaign identifiers | Persists preferences, calculates recipients for an explicitly approved release, and records the outcome of each delivery attempt |
| Moderation and blacklist tools | Account IDs, reason text, relevant server identifiers, ban records or exports, command actor, and Discord audit context | Enforces owner/admin-authorized restrictions, imports/exports data, and performs the moderation operation selected by an authorized user; periodic local ban exports contain banned account IDs |
| Developer commands | Command path, timestamp, actor ID/name, server ID and interaction ID may be written for developer-command audit records | Records attempted developer commands locally and may send an owner-only diagnostic event to the configured private Discord channel |
| Developer metrics | Command names, success/error outcome, duration summaries, exception class names, and daily Discord rate-limit counts | Aggregates records locally for owner-only diagnostics; this database does not include user IDs, server names/IDs, channel IDs, message content, or command arguments |
| OAuth join helper | OAuth authorization code/state during callback, temporary access token and Discord user ID during the request, and the requested server membership operation | Uses the user-approved `identify` and `guilds.join` scopes to request a Discord server join; the helper does not save the token and is separate from ordinary bot use |

Discord may provide more fields to the bot than a particular command needs.
The bot's use of the Discord API, privileged intents, and returned data is
limited by the installed version, granted permissions, enabled intents, and
the feature being used. Removing the bot or revoking permissions prevents
future access through that installation but does not erase information already
stored in the bot's runtime files or messages already delivered through
Discord.

### Information the bot does not intentionally collect for analytics

Developer telemetry is a separate, local aggregate database. Its command
labels identify the command category/name, not the options the user entered.
It records counts, outcome totals, duration sums/sample counts/maxima, error
class names, and daily rate-limit totals. It is not a user-level activity
history, and it is not exported to an advertising, analytics, or AI provider.
The statement that telemetry excludes identifiers does not apply to other
operational files described in this notice: command audit logs, mention
monitor files, update campaign records, suggestions, moderation data, and
server snapshots can contain identifiers or names.

The bot does not use telemetry to score, rank, profile, or make eligibility
decisions about individual users. Moderation or blacklist commands are
separate owner/admin-controlled tools, not automated decisions based on the
aggregate telemetry database.

The local VRChat OSC sender reads the bot heartbeat and this aggregate
telemetry database. When enabled by a Windows launcher, it sends only the
bot's status, version, uptime, heartbeat age, restart count, gateway latency,
server/member totals, instance counts, and seven-day aggregate command/error/
rate-limit figures to the local VRChat OSC chatbox receiver. It does not send
guild names, account identifiers, mention-monitor data, or custom activity
text. The chatbox output may be visible through VRChat's chatbox features; the
sender does not publish the data to a separate analytics service.

### Games, reminders, AI, and music

Game and poll details are feature state, not developer telemetry. A poll
stores its question, options, and user-ID-to-choice votes in memory and shows
the choices and vote totals in its Discord message. Its interactive view
times out after 24 hours. If INFO-level logging is enabled, poll vote log
entries also contain the voter's Discord ID, selected option index, and
whether the vote changed. Tic-Tac-Toe state is held in an interactive view
that times out after 15 minutes. UNO games and music queues are held in
process memory and are not restored after a bot restart; their Discord
messages and any information already delivered to Discord are outside that
memory lifetime.

`/remind` keeps the supplied reminder text and a scheduled task in memory for
the requested delay (1 second through 7 days), then attempts to DM that text
to the requester. The reminder is not saved to a durable queue or runtime
file. A process restart cancels pending tasks, and Discord may prevent or
delay delivery of a DM.

For `/ai talk`, the current code sends the latest user prompt to
`http://localhost:11434/api/generate`; it does not send the stored conversation
history as model context. Prompt/reply pairs are nevertheless accumulated in
an in-memory list associated with the user's Discord ID until the process
restarts. The local endpoint does not itself establish whether a separately
configured Ollama model or proxy forwards prompts elsewhere, so users should
not submit confidential information.

Music commands accept YouTube URLs. The bot uses `yt-dlp` to retrieve metadata
and a stream URL without downloading the media file, then uses FFmpeg and
Discord voice for playback. Track title, webpage/stream URLs, requester
display name, current track, queue, and voice-client state may be held in
memory while the feature runs. YouTube and Discord process requests under
their own terms and privacy disclosures.

### Ban exports and local operational snapshots

The bot attempts a ban export every five minutes. It writes one local
`bans_<server-id>.txt` file per server containing banned Discord user IDs and
a combined `bans_all.txt` file containing server-ID/user-ID pairs. Successful
writes replace the corresponding file; a file for a server that is no longer
connected, or whose export or write fails, may remain stale. These exports
contain identifiers and are not part of aggregate developer telemetry.

Authorized `/manage ban export` and owner-only `/dev ban export` operations
also create files delivered through Discord; the owner export can include ban
reasons. The owner-only `/dev ban import` command reads a supplied attachment
to perform moderation actions. The bot does not intentionally keep the
uploaded attachment as a local archive, but Discord may retain the attachment
and messages under its own rules, and a recipient may save a downloaded
export. Import/export users must have authority to handle the listed accounts
and reasons.

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

### Server snapshots and mention-monitor files

The owner monitor can write a snapshot containing the connected bot's status,
server identifiers and names, member/channel/role counts, owner identifiers,
and whether the bot is present. Mention-monitor files can contain account IDs,
display names, bot flags, aggregate mention counts, and up to 50 recent event
records. The main process also keeps some counters in memory. These records
exist to render local developer dashboards; they are not public analytics
reports. The current code does not establish a fixed deletion period for all
snapshot or mention-monitor fields.

### Operational logs and diagnostic events

The main bot logs warnings and errors to a local rotating log. Error details
can include command/feature names, provider response information, exception
messages, or other context needed to troubleshoot a failure. The bot does not
intend to log passwords, OAuth tokens, authorization codes, or message content
as routine telemetry. A diagnostic path can write developer-command attempt
records containing user identifiers and command paths, and can send a
developer-command event to a configured private Discord channel. These are
distinct from aggregate telemetry and may identify the person who invoked an
owner-only command.

From bot version 1.0.2, the main log rotates daily and retains up to 29
rotated files plus the active file. Rotation is triggered on a subsequent log
write and uses the host's local time; a stopped bot does not rotate files while
it is stopped. Old size-based backups from earlier versions, copies made by
the host, and files copied elsewhere are not automatically deleted by the
current rotation setting.

## 3. Why the information is used and intended legal bases

The bot uses information to respond to commands, run requested features,
enforce permissions, keep operational state after restarts, administer
moderation workflows, send opted-in update messages, deliver member reports,
prevent misuse, and diagnose errors or outages.

| Purpose | Examples of processing | Provisional GDPR basis where GDPR applies |
|---|---|---|
| Provide a command or feature requested by a user | Read the command and necessary options, verify permissions, keep game/poll state, send the result | Article 6(1)(b) only where the processing is objectively necessary for a contract with that user; in other circumstances a different basis must be selected |
| Operate a server-installed feature | Read the administrator's configuration and relevant server context, persist settings, enforce command restrictions | The applicable basis depends on whether the user, server administrator, or another entity determines the purpose and on the relationship between the parties; Article 6(1)(b) is not presumed to cover every server member |
| Deliver optional release notifications | Store a level 0-6 preference, select matching recipients, send and record an explicitly approved release | Article 6(1)(a) is intended for preference-based subscriber messages, subject to valid consent requirements and the user's ability to change or withdraw the choice |
| Receive and route a message report | Read the selected message and context, forward it to the configured moderation channel and configured bot owners | Article 6(1)(f) is a possible basis for a documented, necessary and balanced safety/abuse-prevention purpose; the actual assessment remains to be completed |
| Prevent abuse and protect operation | Check blacklist status and permissions, preserve moderation records, diagnose errors, protect against repeated misuse | Article 6(1)(f) may apply only after the specific interest, necessity, reasonable expectations, impact, safeguards, and objection process have been assessed and documented |
| Produce aggregate developer diagnostics | Count command outcomes and durations and daily rate-limit totals without user or server identifiers | The operator must still determine and record an appropriate basis if these aggregate records are personal data in context; aggregation alone is not a universal legal exemption |
| Perform an OAuth server-join request | Process the authorization callback and ask Discord to add the consenting user to a server | The basis and applicable notice must be determined for the actual helper deployment and user flow; OAuth authorization is not automatically equivalent to every GDPR consent requirement |

These are disclosed as the operator's provisional intended analysis, not a
completed or legally verified allocation. IMY states that the controller must
identify the basis before processing begins, document the choice, and inform
people of it. Where two entities determine purposes and means (for example,
the bot operator and a server administrator), their respective roles and
responsibilities must be assessed rather than assumed.

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

The operator does not claim that consent to use Discord is consent to all bot
processing, that adding the bot to a server establishes a contract with every
member, or that a public notice by itself makes a processing purpose lawful.
If a purpose cannot rely on its stated basis, the operator must change or stop
that processing rather than silently substitute a different basis after
collection.

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
- Reminder tasks, game state, music queues, and AI prompt/reply pairs exist in
  process memory rather than a durable database. Restarting the process loses
  pending reminders and active game/music state and clears the in-memory AI
  history.
- Ban export files are attempted every five minutes and overwritten when a
  replacement write succeeds. A per-server export can remain stale if that
  server is no longer connected or its export/write fails; the code has no
  separate age-based cleanup for those files.
- Message-report destination settings: retained locally per server until an
  administrator changes or disables them.
- Temporary public OAuth authorization state: expires after five minutes and
  can be used once. OAuth access tokens are handled in memory for the join
  request and are not saved by the helper.

The OAuth helper's callback access log omits query values and does not
intentionally print the authorization code, state, token, or user ID. However,
a Discord HTTP error can print up to 1,000 characters of its response body to
the local console, and other network exception text may also be printed.
Protect those diagnostics and review them before sharing.

The table below gives the current operational position in more detail. A
statement that a file has no automatic expiry means the code does not currently
delete it on a time schedule; it is not a promise that the information will be
kept forever or a claim that indefinite storage is appropriate.

| Record or store | Current retention behavior | What may cause deletion or replacement |
|---|---|---|
| Aggregate developer telemetry database | Rows older than the rolling 30-day window are pruned when telemetry is written or a metrics summary is requested | Normal pruning, or manual deletion of the local database and its SQLite sidecar files |
| Current bot log | Daily rotation, up to 29 rotated files plus the active log from version 1.0.2 | Rotation after a log write following the daily boundary; deleting the bot runtime directory or individual files |
| Older bot log backups | Earlier versions used size-based log rotation; old backups are not migrated to the new schedule | Manual review and deletion by the operator |
| Suggestion records | No automatic age-based deletion in the current code | Manual deletion or replacement of the suggestions file by the operator |
| Developer-command attempt records | Appended to a local event file without code-level age-based deletion | Manual deletion or replacement of the runtime event file |
| Update campaign and release state | Preferences, campaign membership/status, delivery attempts, and release queue/status can be retained without a general expiry period | Manual deletion or later campaign-state changes; deleting it may impair duplicate-prevention, progress reporting, or resumption of approved releases |
| Blacklist and moderation/export data | Retained in local runtime or export files while needed for the moderation operation; the code does not provide one automatic expiry for every such file | Authorized removal, overwrite, or manual deletion; Discord may separately retain audit records |
| Periodic ban exports (`bans_<server-id>.txt`, `bans_all.txt`) | The bot attempts to overwrite them every five minutes; per-server files may become stale when an export fails or a server is removed, and no age-based cleanup is implemented | A later successful write replaces a file; otherwise manual deletion |
| Reminder tasks | Held in process memory until delivery is attempted, cancellation, or process shutdown; not written to a durable store | Delivery attempt or process restart; a restart loses pending reminders |
| Polls and games | Poll votes, Tic-Tac-Toe and UNO state are held in memory; poll views time out after 24 hours and Tic-Tac-Toe views after 15 minutes; UNO state has no separate durable retention | View timeout, game completion/cleanup, or process restart; Discord messages may remain |
| AI prompt/reply history | Held in an in-memory per-user list for the process lifetime; the current model request includes only the latest prompt | Process restart; no persistent history file is written by this feature |
| Music queues and active tracks | Track metadata and per-server playback/queue state are held in memory, not persisted as a durable queue | Queue completion, stop/disconnect, or process restart |
| Mention-monitor data and server snapshots | Mention counters and up to 50 recent entries are written to a local monitor file while running; snapshots are rewritten during status updates. No fixed age-based cleanup is implemented for these files | Later writes replace the file; mention counters reset when the bot process starts; manual deletion |
| Owner notification events | Guild-discovery and owner-membership events may be appended locally and relayed by the companion control panel to registered browser push subscriptions; the event file has no code-level age expiry | Manual deletion or rotation outside the bot code; push delivery is handled by the control panel and push providers |
| Message-report channel setting | Stored per server until changed or disabled | Administrator removes or replaces the channel setting, or the operator deletes the local configuration |
| OAuth callback state | One-time state is short lived and expires after five minutes | Automatic expiry or successful one-time use; access token is handled in memory and not saved by the helper |
| Discord report posts, DMs, release posts, and audit records | Stored by Discord and controlled by Discord and the receiving account/server | Deletion by an authorized Discord user or Discord under its own rules; the bot does not control Discord's retention |

SQLite may use write-ahead-log or shared-memory sidecar files while the
database is open. Manual removal of a database should therefore be done only
after the bot is stopped and should include its associated `-wal` and `-shm`
files if present. Deleting a local copy does not delete copies held by Discord,
a recipient, a server administrator, an operating-system backup, or a provider.

Backups, Discord messages, owner DMs, and provider logs may persist beyond the
bot's own runtime files. The operator should review local data periodically and
delete information that is no longer needed, subject to security and legal
requirements.

The operator may preserve limited information longer if reasonably necessary
to resolve a security incident, prevent repeated abuse, maintain an approved
release's delivery integrity, comply with a legal obligation, or establish or
defend a legal claim. This is not a blanket retention period: any such
preservation should be limited to the information and time necessary for that
specific reason, with access restricted.

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
- The Windows launcher may send aggregate bot status and telemetry to the
  local VRChat OSC chatbox receiver. The status sender does not include
  account identifiers, server names, mention-monitor details, or custom
  activity text; chatbox visibility and any platform-side handling are
  governed by VRChat's own features and policies.
- If the separate user-join OAuth helper is run through a Cloudflare Quick
  Tunnel, Cloudflare proxies browser callback traffic to the operator's
  computer. The helper uses Discord's OAuth and API endpoints and handles the
  temporary access token and user ID in memory without saving them. Its
  callback access log omits query values, but a Discord API error can cause
  up to 1,000 characters of the response body to be printed to the local
  console; other network exceptions may also be printed. Protect those local
  diagnostics and do not assume error output can never contain personal data.
- The policy files are hosted in the public GitHub repository
  `eliastudent-sketch/info`. No GitHub Pages website is currently deployed.

These providers operate under their own terms and privacy practices. Their
processing may occur in countries other than the user's or operator's country.
The operator has not established a complete provider-by-provider map of
international transfer mechanisms; provider-specific details should be
checked in the relevant provider's privacy documentation.

The operator does not sell personal data and does not use a third-party
analytics service for developer telemetry.

### Who may receive or access information

Depending on the feature, information may be visible to:

- **Discord:** as the platform carrying commands, interactions, bot messages,
  moderation reports, update messages, and OAuth authorization. Discord
  processes information under its own terms and privacy disclosures.
- **The server administrator and moderators:** when they configure the bot,
  view server data returned by a command, or receive a report in their
  configured private report channel. The server controls channel permissions
  and moderator access.
- **Configured bot owners:** for owner-only diagnostics, developer-command
  alerts, operational release messages, and the owner DM copy of a member
  report. Access to the operator's computer also provides access to local
  runtime files.
- **YouTube or media infrastructure:** only when a media feature requests
  public media metadata. The provider may receive the query or media URL
  needed to retrieve that information.
- **Cloudflare:** only if the optional OAuth helper is exposed using a
  Cloudflare Quick Tunnel. Cloudflare may process connection and request
  metadata as it proxies the browser callback. The helper is not required for
  ordinary bot use.
- **GitHub:** the two policy documents are published in a public GitHub
  repository. Viewing the public repository is subject to GitHub's own
  processing; the bot's runtime telemetry database is not uploaded there.

The optional local Ollama integration runs on the operator's computer as
configured. The operator does not intentionally send local developer
telemetry to Ollama. A user prompt submitted to that feature may be processed
by the local model because that is the purpose of the feature; whether a
separate model service is configured is a deployment-specific fact.

The operator does not intentionally sell personal data, rent member lists, or
send developer telemetry to an advertising network, external analytics
service, or external AI provider. Information may still be disclosed when
necessary to comply with law, respond to a valid legal request, protect a
person's vital interests, or investigate a credible security or abuse incident,
subject to applicable law.

### International processing

The operator is based in Sweden, but Discord and other providers may process
information in other countries. The precise provider entities, hosting
locations, onward recipients, and transfer safeguards depend on each
provider's current service configuration and terms. The operator has not
completed a full transfer map or documented transfer mechanism for every
provider and feature. Where the GDPR requires a transfer safeguard, the
operator must identify and apply it before relying on that transfer. Users
should consult the linked provider notices for the provider's own information
about locations and safeguards.

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

### What to include in a request

State that you are making a privacy request and describe the right you wish to
exercise. Include the Discord account identifier needed to locate the relevant
records, the server or feature involved if known, and a safe way to reply.
Do not send passwords, authentication codes, bot tokens, OAuth codes, or
unnecessary sensitive information. The operator may ask for proportionate
additional information if needed to distinguish you from another account or
protect another person's information. The operator should not ask for more
information than is reasonably needed to verify the requester.

### How requests are handled

The operator will review a request, search the local stores reasonably
available, and respond within the deadline required by the law that applies.
For GDPR requests, the usual response period is one month; where the law
allows an extension because of complexity or number of requests, the
requester should be informed within the initial period. A request is not
automatically refused because the bot has been removed from a server or
because a user has stopped using Discord.

The response may explain that a record is held by Discord or a server
administrator rather than in the operator's files. The operator cannot
directly edit another person's account, delete a message from a server where
the operator lacks the necessary access, or control a recipient's copy of a
report. Where possible and appropriate, the operator will identify the
relevant recipient or provider so the requester can contact them.

### Rights and their limits

Depending on the applicable law and circumstances, a person may ask for:

- **Access:** confirmation whether personal data is being processed and a
  copy of the personal data and required supporting information.
- **Correction:** correction of inaccurate data and completion of incomplete
  data, such as a saved preference or identifier.
- **Deletion:** deletion when a legal ground for erasure exists. Deletion may
  be limited by another person's rights, a legal obligation, a need to retain
  evidence of abuse or security events, or data held independently by Discord
  or a server administrator.
- **Restriction:** limiting certain processing while a dispute about
  accuracy, lawfulness, or an objection is assessed, where the applicable
  conditions are met.
- **Objection:** objecting to processing based on legitimate interests. The
  operator must assess the objection under the applicable law and stop that
  processing unless a legally sufficient reason to continue applies.
- **Portability:** receiving data the requester provided in a structured,
  commonly used, machine-readable format, where the legal conditions for
  portability are met. This right does not apply to every record or legal
  basis.
- **Withdrawal of consent:** changing or withdrawing an update preference.
  This stops future preference-based update DMs after the change is applied;
  it does not make earlier processing unlawful or delete a message already
  delivered.
- **Complaint:** contacting the supervisory authority with jurisdiction. A
  person in Sweden may contact [IMY](https://www.imy.se/). Residents elsewhere
  may have a right to complain to their local authority.

These are not unconditional rights to delete every copy or stop every
operation. The applicable law sets the conditions, exceptions, and response
obligations. Nothing in this notice limits a right that cannot lawfully be
limited.

## 7. Children

The bot does not request a date of birth or independently verify age, and it
does not have a separate bot-level age gate. Users must meet Discord's current
age requirements and any requirements that apply where they live.

Swedish law sets age 13 for a child's own consent only where an
information-society service is offered directly to that child and consent is
the legal basis; this is not a universal minimum age for every service or
processing purpose. The operator does not claim that this rule alone resolves
all age or children's-data obligations for a globally accessible bot.

The bot is not represented as a child-directed service. It does not knowingly
ask children to submit age, school, address, or other special personal details.
However, users may submit content in commands or reports, and the operator
cannot infer a user's age reliably from a Discord ID. Parents or guardians
who believe a child has supplied personal information may contact the operator
through the support server and identify the relevant account and feature
without posting the child's information publicly. If the operator learns that
data was collected in circumstances requiring parental consent or another
child-specific safeguard, the operator should stop or restrict the relevant
processing until the issue is addressed.

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
