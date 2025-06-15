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

### Startup Behavior
- Application runs as a background Windows Service
- Service auto-starts on Windows boot
- Cannot be disabled via normal user privileges

### Uninstallation
- A separate uninstaller utility
- Remove application binaries
- Remove all configuration files
- Delete all Windows registry entries made during installation

### Branding & Identity
Support the inclusion of:
- Company Name
- Product Name
- Logo
- Contact details of the application provider

Branding must appear in:
- Application UI
- Wizard screens
- Installer/uninstaller
- About section

## User Interface Requirements

### General UI
- Intuitive and modern Windows desktop UI
- Responsive and adaptive layouts for varying screen sizes

### Wizard UI for Backup Job Creation
- Clear, step-by-step navigation
- Input validation at each step
- Progress indicator

### Backup Job Dashboard
List view of all jobs with columns:
- Job Name
- Last Run Time
- Next Scheduled Run
- Status (Success/Failure)
   
Options:
- Run Now
- Edit
- Delete

## Security Requirements

- OAuth2 or similar secure token-based authentication for cloud services
- All user credentials and tokens must be stored securely (encrypted at rest)
- Activity logs should not contain sensitive credential data

## Edge Case Handling

If files are open/locked during scheduled backup, the application must still back up files using:
- VSS (Volume Shadow Copy Service) or equivalent methods

Network unavailability:
- Retry mechanism
- Log failure with descriptive message

## Assumptions & Constraints
- An Internet connection is required for cloud uploads
- The application will not support any OS outside of the mentioned Windows versions
- No cloud storage other than Google Drive and OneDrive is supported in v1.0

## Project Completion
- Windows application installer
- Background service executable
- Uninstaller utility
- User manual/guide
- Application logo and branded UI
- Support contact info within the application
- Maintenance Warranty
- Source Code

## Future Considerations (Out of Scope for v1.0)

- Support for other cloud storage providers (Dropbox, AWS S3, etc.)
- File encryption before backup
- Backup compression
- Restore functionality from the cloud to the local machine
- Support login and integration with: Google Drive & Microsoft OneDrive
- OAuth2-based secure login embedded within the application.
- Licensing feature
