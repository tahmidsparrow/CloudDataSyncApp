# CloudDataSyncApp

A Windows-based application that securely backs up critical data from local machines to cloud storage services, including Google Drive and Microsoft OneDrive. It supports both scheduled and manual backups, offers retention policy management, and features a user-friendly wizard-driven interface.

## Target Platform
Operating Systems Supported:
- Windows 8.1 (64-bit)
- Windows 10 (64-bit)
- Windows 11 (64-bit)

## Functional Requirements
### Core Features:
Cloud Integration - Integration with:
- Google Drive
- Microsoft OneDrive

### Backup Job Wizard
- User authentication
- Select source folder(s) / file(s)
- Select the destination folder on the cloud
- Set backup execution schedule (daily, weekly, custom time)
- Define retention period (in days) - Implements FIFO logic: older backups are deleted as new ones are added
- Assign a name to the backup job

### Backup Execution
- Scheduled backups executed based on user-defined time
- Manual execution of the backup job by the user at any time
- Ability to back up even when files are in use (via shadow copy/file locking mechanism)

### Backup Job Management
- View all existing backup jobs
- Edit/modify existing jobs
- Delete backup jobs

### Logging
Log file generated for every backup job run
- Log success/failure status
- Include timestamps, errors (if any), and file-level operation info


## Non-Functional Requirements

