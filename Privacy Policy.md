# Privacy Policy

**Draft — effective date: October 11, 2026**

This Privacy Policy describes how the Discord bot operated under the public
name `buttercup_uwu` handles information when it is used in Discord servers,
through commands, games, moderation tools, reminder features, and update
notifications. It also explains what information is stored on the host system,
what is processed by Discord and other third parties, and how users can contact
operator for questions, requests, or concerns.

This document is intentionally written as a public, plain-language summary for
an operator-managed bot that is not open-sourced and is run in a closed-source
deployment. It should be checked against the actual bot deployment, enabled
features, host configuration, and applicable local law before publication.

## 1. Operator and contact details

- **Public operator name:** `buttercup_uwu`
- **Discord account:** [buttercup_uwu](https://discord.com/users/564486880763183111) (ID `564486880763183111`)
- **Support and privacy requests:** [Discord support server](https://discord.gg/uP8FVT3yaZ)

The bot is operated by the public operator identified above. The operator may
be a person or organization using a public Discord identity rather than a
formal legal name. This public disclosure does not waive any legal disclosure
requirements that may apply in the operator's jurisdiction or where the bot is
made available.

**TODO — legal operator disclosures:** Confirm whether the laws that apply to
the operator or users require a legal name, mailing address, business details,
or other contact information in addition to this public Discord contact. Do not
assume that using a pseudonym removes any such requirement. Obtain legal advice
if uncertain; no private identity or address is supplied or implied here.

## 2. Scope of this policy

This policy applies to the bot's activities in connection with Discord servers,
commands, DMs, reactions, automated announcements, and runtime files created by
or for the bot. It does not replace Discord's own Privacy Policy, Terms of
Service, or platform controls. The bot processes some data because Discord makes
that information available to bot accounts in the course of carrying out a
server feature, command, or automation.

Where Discord or a third-party service processes personal information separately,
that party's own terms and policies apply.

The bot may be configured differently in different deployments. The features
that are actually enabled on a given host may materially affect what data is
collected and retained. The operator should therefore review this policy and the
host configuration whenever features are added or removed.

## 3. Information the bot may process

The bot uses Discord's API and therefore may interact with information that
Discord provides to authorized bot accounts. Depending on how the bot is used
and which features are enabled, the bot may process or store the following
categories of information.

### 3.1 Discord account and server information

The bot may process:

- Discord user IDs, usernames, display names, and account identifiers
- Server IDs, server names, guild membership data, and related metadata
- Channel IDs, channel names, category membership, and permissions context
- Role IDs and role names where needed for bot functions and moderation
- Message IDs, timestamps, authors, and message metadata involved in commands
- Reaction data, including reaction emoji and counts used for polls or prompts
- Server membership counts, ownership details, and operational server snapshots

This information is generally needed for the bot to respond to commands,
check permissions, inspect server state, and carry out member-specific or
server-specific features.

### 3.2 Update-notification campaign data

The bot includes an update-notification prompt system that may post one
announcement in a configured announcement channel and attempt to DM each unique
human user found in the servers in which the bot account is present. The bot
may track:

- the user's Discord user ID
- a DM channel ID and DM message ID for the opt-in prompt
- a delivery status such as pending, sending, sent, failed, or left_server
- the time the DM was sent or last processed
- the selected update-preference level (0 through 6)
- whether multiple choices were detected and whether a conflict needs review
- the source of the selection (for example, DM, announcement, or conflict)
- a record that the bot skipped bot accounts and avoided duplicate sends

These records are kept in a runtime file to resume after restart, reconcile
reactions, and avoid sending the same user multiple DMs in the same campaign.
The bot may also store the configured guild ID, channel ID, server IDs, and the
announcement message ID used for the notification campaign.

### 3.3 Mention statistics

The bot may produce mention statistics when a feature is enabled. This may
include:

- author IDs and mentioned-user IDs
- display names or usernames involved in the event
- server names and IDs
- timestamps
- counts of mention activity
- a recent summary or rolling record of mention events

The mention-statistics handler does not deliberately store the full text of the
message content, although the feature may still rely on Discord message metadata
that Discord provides to the bot as part of the event.

### 3.4 Operational and health data

The bot may store operational and diagnostics information such as:

- health or heartbeat records
- bot uptime or activity counters
- restart counts and timestamps
- connected server counts
- server snapshots, including names, IDs, owner IDs, and counts of members,
  channels, and roles
- operational notification events and failure records
- bot runtime metadata necessary to troubleshoot startup or runtime issues

This information is relevant for bot monitoring, troubleshooting, and ensuring
that a bot deployment remains operational.

### 3.5 Moderation and blacklist data

When moderation features are used, the bot may process:

- user IDs targeted by a moderation command
- reasons for a blacklist or ban action
- export metadata related to banned users or moderation records
- audit information needed to administer a blacklist or export feature

If the periodic export task is enabled, the bot may write ban-related IDs to a
host filesystem location. A user-invoked export may include additional fields,
including ban reasons, depending on the feature and deployment.

### 3.6 Commands and user-submitted content

The bot may process information supplied through commands, including:

- reminder text
- URLs or links
- game choices or poll options
- custom descriptions or notes entered by users
- moderation commands or parameters
- command arguments needed to complete the requested action

Some of this information is transient and may be held in memory while the bot
process runs, while other values may be persisted in runtime state or logs
depending on the feature and deployment.

### 3.7 Audit and runtime records

The bot may create runtime records for reliability and operational purposes,
including:

- the state of current campaign prompts
- deliverability status and owner metadata
- pending tasks or reminders
- runtime state files in the bot's runtime directory
- generated export files and internal bot records

The bot's current behavior does not define a universal deletion schedule for
all runtime files. Files may be overwritten, retained until manually deleted,
or retained by host backups, logs, or other operational systems outside the bot's
own code.

## 4. Purposes of processing

The bot processes information for the following general purposes:

- to provide Discord commands, polls, games, and utility features
- to fulfill reminder tasks and any scheduled or user-requested notification
- to send update-preference prompts and avoid duplicate DMs
- to record update choices for later reconciliation after restart
- to support server moderation and authorization workflows
- to monitor the health and status of the bot and connected servers
- to troubleshoot errors, service disruptions, or bot startup issues
- to generate operational summaries and host-side audit records
- to support the bot's functions where you or a server administrator explicitly
  requested them

The bot is not primarily a general-purpose data-collection service. It handles
information to operate the features requested by users and administrators in the
Discord environment.

## 5. How information is used

In practical terms, the bot may use the information described above to:

- identify the user or server making a request
- check whether a command is allowed in a given channel or guild
- determine whether a member has already received a campaign DM
- reconcile reactions to update-notification prompts after restart
- maintain operational records that help the bot recover from failures
- join or correlate entries across runtime files used by the bot
- support security, abuse prevention, moderation, and operational integrity

The bot does not claim to be a full-scale analytics service or a commercial
data broker. Its use of information is tied to the functions it offers and the
Discord environment in which it runs.

## 6. Data minimization and retention

The operator aims to process only data needed for the features being used, but
this document does not guarantee that every deployment or host configuration uses
strict minimization in the same way. The following practices describe the bot's
current observed behavior and should be confirmed against the actual deployment.

- Runtime state files are kept in the host's runtime directory for bot
  operations such as update prompt tracking.
- Some reminder, game, and poll state are held in memory and may be lost if the
  bot process restarts or stops.
- Mention statistics are retained in a limited rolling summary and may not store
  full message text.
- Blacklist and export information may persist until a host admin deletes it or
  the feature overwrites it.
- Ban-export files, when enabled, may be stored on the host filesystem and may
  be rewritten by later iterations of the export task.
- Backups, logs, and host-side retention settings may extend the lifetime of a
  file beyond the bot's internal state logic.

There is no single automatic deletion schedule that applies to all runtime
records across all deployments. A host operator, hosting provider, or server
administrator may choose to rotate, archive, or remove files according to their
own practices. Any request to delete or correct bot-held information should be
made to the operator through the contact methods in this policy.

## 7. Sharing and third-party services

The bot communicates with Discord to provide its features.

The bot may also interact with third-party services or libraries in specific
features, including media metadata fetching through tools such as `yt-dlp`.
Specific hosting providers and external service operators depend on the
deployment and are not identified in this policy as a universal statement about
all installations.

The operator should identify relevant hosting providers and any external
services before publication of a public policy if the deployment depends on them.

The bot does not sell personal information as a core feature. However, the
operator must verify the actual hosting and data-processing arrangements in any
specific deployment. No external service guarantees that user data will never be
accessed or retained by that service under its own policies.

## 8. No sale of personal information and no general data brokerage

The bot does not describe itself as a general-purpose data broker and does not
advertise a feature that sells user identifiers or server data. The bot may,
nonetheless, use data for operational, moderation, reminder, or communication
features described in this policy.

The operator should not represent that no third-party processing occurs in a
particular deployment unless the actual host and connected services are checked.
A bot hosted on a cloud provider or using external libraries may give that
provider access to runtime files or logging data according to the provider's
terms and the host's configuration.

## 9. Your choices and rights

Members may choose level 0 (no updates) or levels 1–6 in the update prompt and
may change or remove their reaction. The bot may also reconcile conflicting
choices when more than one selection is detected.

To ask about, correct, or request deletion of bot-held information, contact the
operator through the public Discord support server. Requests may need to be
assessed under applicable law, and some records may need to be retained for
security, legal, or operational reasons.

Discord-held copies, such as messages or user profile data that belong to the Discord
platform rather than the bot's own runtime files, must be addressed through
Discord's own support or privacy channels.

## 10. Security

The operator should restrict access to bot tokens, credentials, runtime files,
and host systems, and should use appropriate file permissions, secret management,
updates, backups, and security controls. A bot that is connected to Discord
servers should be treated as an internet-connected system and should be hosted
in a manner consistent with security best practices.

This section describes reasonable safeguards and operational practices, not a
promise or certification that any specific deployment is secure. No
internet-connected service can guarantee absolute security or permanent data
integrity.

## 11. Children and age requirements

The bot is not intended to evade Discord's age requirements or any minimum-age
rules that apply where a user lives. Parents or guardians should review the bot
and the Discord environment before allowing a child to interact with it.

The operator should comply with applicable age restrictions and local laws where
the service is offered.

## 12. Legal rights and jurisdiction-specific disclosures

Rights and required notices vary by jurisdiction. As a result, a privacy policy
for a public bot may need to include additional disclosures about controller
identity, lawful basis for processing, retention periods, international transfers,
request procedures, regulator contacts, or local representative information,
depending on the laws that apply.

**TODO — jurisdiction-specific privacy terms:** Determine and add any legally
required disclosures about the operator/controller identity, legal bases,
retention periods, international transfers, privacy rights, regulator contacts,
or local representative. Do not infer these details from the public handle or
from this software description; obtain advice where necessary.

## 13. Data deletion and limitations

Because the bot stores some data in runtime files and may rely on Discord and
third-party services, deletion is not always immediate or fully under the bot's
control.

If a record is stored in the bot's runtime directory, the operator may delete it
manually. If a copy exists in Discord or a backup or log system, that copy may
remain subject to the relevant provider's policies and retention settings.

The Operator may not be able to guarantee deletion of data already copied or
stored elsewhere in the Discord ecosystem or host environment.

## 14. Changes to this policy

The operator may update this Privacy Policy when the bot, its deployment,
or its data practices change. The effective date at the top should be revised
for material changes. The operator should also review this document when a host
provider, feature set, moderation workflow, or retention practice changes.

Continued use of the bot after a revision is published is a sign that the user
accepts the updated terms to the extent permitted by applicable law.

## 15. Contact and further questions

For questions, privacy concerns, access requests, or operational issues,
contact the operator through the [Discord support server](https://discord.gg/uP8FVT3yaZ).

Do not send confidential or highly sensitive personal information through a public
Discord channel. If a security or abuse issue needs to be reported, do so in a
private channel or through the operator's designated secure contact method if
one exists.

This Privacy Policy is a draft and may require additional legal review before it
is made public. It does not attempt to replace advice from a lawyer or the local
legal requirements that apply to the operator and users in the jurisdiction where
service is offered.
