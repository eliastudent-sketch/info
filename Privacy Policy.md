# Privacy Policy

**Effective date: October 11, 2026**

This Privacy Policy explains how the Discord bot operated under the public name `buttercup_uwu` handles information when it is used in Discord servers and direct messages. The bot provides server utilities, reminders, moderation workflows, polling and game features, announcement tools, and operational automation. This document describes the practices of the current deployment and the data that may be created, processed, stored, or transmitted by the bot while it is operating.

This policy applies to the bot as it is deployed and configured by the operator. It does not replace Discord's own Privacy Policy, Terms of Service, or platform controls. Where Discord or another third party handles personal information separately, that service's own terms and data practices apply.

## 1. Operator and contact details

- **Public operator name:** `buttercup_uwu`
- **Discord account:** [buttercup_uwu](https://discord.com/users/564486880763183111) (ID `564486880763183111`)
- **Support and privacy requests:** [Discord support server](https://discord.gg/uP8FVT3yaZ)

The bot is operated by the public operator identified above. The operator may be an individual or a small operation using a public Discord identity rather than a formal legal entity. This document is meant to be a plain-language explanation of the bot's practical data handling and does not waive any legal disclosure requirements that may apply in the operator's jurisdiction or where the bot is offered.

## 2. Scope of this policy

This policy covers information processed by the bot in connection with Discord servers, direct messages, interactions, announcements, moderation commands, reminder tasks, and runtime state used to maintain bot operation.

The bot may be configured differently across deployments. The exact data collected and retained depends on the version of the bot, enabled features, host configuration, server permissions, and the operator's operational choices. This policy therefore applies to the bot's actual deployment and should be read together with the host environment and the bot's real feature set.

## 3. Information the bot may process

The bot uses Discord's API and therefore may receive and process information that Discord makes available to a bot account. Depending on the features enabled in a server and the commands used, the bot may process or store the following categories of information.

### 3.1 Discord account and server information

The bot may process:

- Discord user IDs, usernames, display names, and account identifiers
- Server IDs, server names, guild membership data, and related metadata
- Channel IDs, channel names, category information, and permission context
- Role IDs and role names where needed for moderation, access checks, or bot features
- Message IDs, timestamps, authors, and message metadata involved in commands or interactions
- Reaction data, including emoji and counts used for prompts, polls, or campaign choices
- Server membership counts, ownership details, and other operational server snapshots

This data is generally needed to respond to commands, check permissions, inspect server state, and carry out member-specific or server-specific features.

### 3.2 Reminder and scheduled-task data

When reminder features are used, the bot may process:

- the reminder author's Discord user ID
- reminder text or notes entered by the user
- the target channel or DM destination for delivery
- reminder timestamps and scheduling data
- reminder delivery state, including pending or sent status
- any runtime metadata used to keep the reminder queue or state consistent

Some reminder data is transient and may exist only in memory while the process runs. Other records may be kept in runtime files so that reminders or bot state can survive a restart or a brief interruption.

### 3.3 Update-notification campaign data

The bot may include an update-notification workflow that posts an announcement in a configured announcement channel and, where enabled and permitted under applicable Discord rules, may attempt to send a direct message to a user who is eligible and has a valid basis for contact. In all cases, the deployment should only contact a user where the relevant permission, opt-in, or legal basis exists.

If this feature is enabled, the bot may track:

- the user's Discord user ID
- a DM channel ID and DM message ID for the opt-in prompt
- a delivery status such as pending, sending, sent, failed, or left_server
- the time the DM was sent or last processed
- the selected update-preference level (0 through 6)
- whether multiple choices were detected and whether a conflict needs review
- the source of the selection (for example, DM, announcement, or conflict)
- a record that the bot skipped bot accounts and avoided duplicate sends

These records are kept in a runtime file to resume after restart, reconcile reactions, and avoid sending the same user multiple DMs in the same campaign. The bot may also store the configured guild ID, channel ID, server IDs, and the announcement message ID used for the notification campaign.

This feature is operational; it does not create a general-purpose marketing or tracking system. The bot should not assume that a public announcement or appearance in a server establishes a valid basis to send direct messages. If a deployment cannot confirm the required consent or policy basis, it should treat the user as not eligible and avoid direct contact.

### 3.4 Mention statistics

The bot may generate mention statistics if that feature is enabled. This may include:

- author IDs and mentioned-user IDs
- display names or usernames involved in the event
- server names and IDs
- timestamps
- counts of mention activity
- a recent summary or rolling record of mention events

The mention-statistics handler does not intentionally store the full text of message content, although the feature may still rely on Discord message metadata that Discord provides to the bot as part of the event.

### 3.5 Moderation and blacklist data

When moderation features are used, the bot may process:

- user IDs targeted by a moderation command
- reasons for a blacklist, timeout, or ban action
- export metadata related to banned users or moderation records
- audit information needed to administer a blacklist or export feature

If the periodic export task is enabled, the bot may write ban-related IDs to a host filesystem location. A user-invoked export may include additional fields, including ban reasons, depending on the feature and deployment.

### 3.6 Commands and user-submitted content

The bot may process information supplied through commands, including:

- reminder text
- URLs or links
- game choices or poll options
- custom descriptions or notes entered by users
- moderation commands or parameters
- command arguments needed to complete a requested action

Some of this information is transient and may be held in memory while the bot runs. Other values may be persisted in runtime state or logs depending on the feature and deployment.

### 3.7 Operational and health data

The bot may store operational and diagnostics information such as:

- health or heartbeat records
- bot uptime or activity counters
- restart counts and timestamps
- connected server counts
- server snapshots, including names, IDs, owner IDs, and counts of members, channels, and roles
- operational notification events and failure records
- bot runtime metadata needed to troubleshoot startup or runtime issues

This information is relevant for bot monitoring, troubleshooting, and ensuring the system remains operational.

### 3.8 Audit and runtime records

The bot may create runtime records for reliability and operational purposes, including:

- the state of current campaign prompts
- deliverability status and owner metadata
- pending tasks or reminders
- runtime state files in the bot's runtime directory
- generated export files and internal bot records

These runtime files are part of the operational environment and may be retained until overwritten, deleted manually, or removed by host-side backups or maintenance processes.

## 4. Purposes of processing

The bot processes information for these general purposes:

- to provide Discord commands, utilities, polls, games, reminders, and moderation features
- to fulfill reminder tasks and any scheduled or user-requested notification
- to send update-preference prompts and avoid duplicate DMs
- to record update choices for later reconciliation after restart
- to support server moderation and authorization workflows
- to monitor the health and status of the bot and connected servers
- to troubleshoot errors, service disruptions, and bot startup issues
- to generate operational summaries and host-side audit records
- to support features that a server administrator or user explicitly requested

The bot is not a general-purpose analytics service or a commercial data broker. It processes information to operate the features requested by users and administrators within the Discord environment.

## 5. How information is used

The bot may use the information described above to:

- identify the user or server making a request
- determine whether a command is allowed in a given channel or guild
- determine whether a member has already received a campaign DM
- reconcile reactions to update-notification prompts after restart
- maintain operational records that help the bot recover from failures
- join or correlate entries across runtime files used by the bot
- support security, abuse prevention, moderation, and operational integrity

## 6. Data minimization and retention

The operator aims to process only the data needed for the features being used, but the exact retention behavior depends on the deployment and host environment. The bot's current operational practices are described below.

- Runtime state files are kept in the host's runtime directory for bot operations such as reminder tracking and update-prompt tracking.
- Some reminder, game, and poll state is kept in memory and may be lost if the bot process restarts or stops.
- Mention statistics are retained in a limited rolling summary and may not store full message text.
- Blacklist and export information may persist until a host admin deletes it or the feature overwrites it.
- Ban-export files, when enabled, may be stored on the host filesystem and may be rewritten by later iterations of the export task.
- Host backups, logs, and server-side retention settings may extend the lifetime of runtime data beyond the bot's internal logic.
- There is no single automatic deletion schedule applicable to every deployment.

Any request to delete or correct bot-held information should be made through the public contact methods listed in this policy. Some records may need to be retained for security, moderation, legal, or operational reasons.

## 7. Sharing and third-party services

The bot communicates with Discord to provide its features.

The bot may also interact with third-party services or libraries in specific features, including media metadata fetching through tools such as `yt-dlp`. Hosting, logging, backups, and external services depend on the deployment and are not always the same across installations.

The operator should identify relevant hosting providers and external services before publication of a public policy if the deployment depends on them. In practice, the bot may rely on:

- Discord, for bot API access and server data
- the host provider or virtual private server provider, for runtime storage and system access
- backup or logging services configured by the host operator
- any external media or content service used by a feature

The bot does not sell personal information as a core feature. However, the operator must verify the actual hosting and data-processing arrangements in each specific deployment. No external service guarantees that user data will never be accessed or retained under its own policies.

## 8. No sale of personal information

The bot does not describe itself as a general-purpose data broker and does not advertise a system that sells user identifiers or server data. The bot may nonetheless use data for operational, moderation, reminder, communication, or maintenance features described in this policy.

The operator should not represent that no third-party processing occurs in a particular deployment unless the actual hosting environment and connected services have been reviewed.

## 9. Your choices and rights

Users may choose update-preference level 0 (no updates) or levels 1–6 in the update prompt and may change or remove their reaction. The bot may reconcile conflicting choices when more than one selection is detected.

To ask about, correct, or request deletion of bot-held information, contact the operator through the public Discord support server. Requests may need to be assessed under applicable law, and some records may need to be retained for security, legal, or operational reasons.

Discord-held data, such as message content or account profile data that belongs to the Discord platform rather than the bot's own runtime files, should be addressed through Discord's own support or privacy channels.

## 10. Security

The operator should restrict access to bot tokens, credentials, runtime files, and host systems, and should use appropriate file permissions, secret management, updates, backups, and security controls. A bot connected to Discord servers should be treated as an internet-connected system and should be hosted in a manner consistent with security best practices.

This section describes reasonable safeguards and operational practices, not a promise or certification that any specific deployment is secure. No internet-connected service can guarantee absolute security or permanent data integrity.

## 11. Children and age requirements

The bot is not intended to evade Discord's age requirements or any minimum-age rules that apply where a user lives. Parents or guardians should review the bot and the Discord environment before allowing a child to interact with it.

The operator should comply with applicable age restrictions and local laws where the service is offered.

## 12. Legal rights and jurisdiction-specific disclosures

Rights and required notices vary by jurisdiction. Privacy laws may require additional disclosures about controller identity, lawful basis for processing, retention periods, international transfers, request procedures, regulator contacts, or representative information, depending on where the bot is used.

This policy is designed as a practical, plain-language disclosure for a single-operator Discord bot. If local law imposes additional requirements, the operator will update this document to reflect those legal requirements and the actual deployment setup.

## 13. Data deletion and limitations

Because the bot stores some data in runtime files and may rely on Discord and third-party services, deletion is not always immediate or fully under the bot's control.

If a record is stored in the bot's runtime directory, the operator may delete it manually. If a copy exists in Discord or a backup or log system, that copy may remain subject to the relevant provider's policies and retention settings.

The operator should review and respond to deletion requests in a manner consistent with applicable law, Discord policy, and the operational requirements of the host environment. Where a request is denied or partially fulfilled because of security, legal retention obligations, or an external provider's own rules, the operator should explain the reason as clearly as practicable and retain only what is necessary.

The operator may not be able to guarantee deletion of data already copied or stored elsewhere in the Discord ecosystem or host environment.

## 14. Changes to this policy

The operator may update this Privacy Policy when the bot, its deployment, or its data practices change. The effective date at the top should be revised for material changes. The operator should also review this document when a host provider, feature set, moderation workflow, or retention practice changes.

Continued use of the bot after a revision is published is a sign that the user accepts the updated terms to the extent permitted by applicable law.

## 15. Contact and further questions

For questions, privacy concerns, access requests, or operational issues, contact the operator through the [Discord support server](https://discord.gg/uP8FVT3yaZ).

Do not send confidential or highly sensitive personal information through a public Discord channel. If a security or abuse issue needs to be reported, do so in a private channel or through the operator's designated secure contact method if one exists.

This Privacy Policy is intended to describe the operator's current practices and should be reviewed against any additional legal requirements applicable to the operator and users in the jurisdiction where the service is offered. It does not replace advice from a lawyer where formal legal review is necessary.

