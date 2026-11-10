# BugHunter Pro — Privacy Policy

Effective date: 10 November 2026  
Application version covered: 1.0.0  
Publisher: Aria Vision  
Microsoft Store product ID: 9NWWZ8MDJ4M0

BugHunter Pro is a Windows desktop workspace for authorized security configuration reviews. This policy explains the information processed by the application, the network connections it makes, and the controls available to you.

## 1. Information processed by the application

The application stores the projects, descriptions, exact allowed hosts, target URLs, authorization and testing notes, and other content you enter or import. It also stores your preferences, project activity, scan times, selected checks, scope and configuration snapshots, request counts, scan status, observations, and findings with evidence, severity, review status and remediation notes.

Scans process selected HTTP response headers, HTTP status codes, cookie attribute metadata, and TLS certificate and connection metadata. Depending on the target, these records can contain domain names, IP addresses, URL paths, cookie names, certificate subjects or issuers, and other identifiers. Information you enter manually may include personal or confidential information. Only enter information necessary for your authorized work; avoid passwords, access tokens and unrelated sensitive personal information.

The scanner does not read or save response bodies. Cookie values received in response headers are processed transiently to inspect attributes; their values are not saved or replayed in later requests. Selected header values are shortened and some sensitive patterns are redacted, but these measures do not guarantee removal of every identifier or secret a server might return. Target URLs containing credentials, query strings or fragments are rejected. The application does not provide an authenticated scanning or credential-storage feature.

## 2. Local storage and its protection

Workspace records and preferences are stored in a local SQLite database named `bughunter.db`. The normal workspace folder is `%LOCALAPPDATA%\BugHunterPro`. A custom data directory may be selected through launch configuration. Windows package storage redirection may affect the physical location of a Store installation; use **Settings → Open data folder** to locate the workspace actually in use.

The application also creates a workspace lock file and rotating local diagnostic logs. Diagnostics record event names, timestamps, severity and error types; the application logging formatter omits request URLs, response contents and exception text. A log rotates at approximately 1 MB, with up to three retained rotated files.

BugHunter Pro does not encrypt its database, logs, exports or backups. Their protection depends on your Windows account, file permissions, device encryption and the locations you choose. Other software or people with access to those files may be able to read them. The publisher does not automatically receive your workspace or diagnostic files.

## 3. Network connections and information transmitted

Creating and reviewing projects, findings and reports does not require an application account or a publisher-hosted service. When you explicitly authorize and start a scan, the application sends bounded HTTP GET or HEAD requests and/or makes TLS connections to the configured, in-scope target. Redirect destinations are checked against the configured scope before a further request is sent. DNS resolution may occur through your system's configured resolver.

Target operators can receive your public or network IP address, the requested host and URL path, request method, connection details, and standard request headers including the BugHunter Pro user agent. DNS providers and network operators may also observe relevant connection information. HTTPS uses certificate validation; HTTP traffic is not encrypted. A path you supply is transmitted as part of the request, so do not include secrets or personal information in it. The app does not upload your project database, notes, reports or findings to the publisher as part of a scan.

You control whether to scan, which authorized targets and checks to use, and the request limits and timing. You can cancel a scan; an already initiated connection, TLS check or system DNS lookup may take time to finish. Restrict your scope to systems you are authorized to test.

The optional local demo runs a temporary HTTP server bound to `127.0.0.1` on your own device. Its demo scans stay on the local loopback connection. The server stops when the application closes. Other processes on the same device may reach that loopback endpoint while it is running.

## 4. Third parties, analytics and telemetry

This version has no application analytics, advertising SDK, telemetry upload, cloud synchronization, remote AI service or publisher-operated backend. Its third-party libraries, including PySide6/Qt, SQLAlchemy, HTTPX and ReportLab, provide local application, networking, database and report functionality; using them does not by itself create accounts with those projects or send your workspace to them.

Your chosen scan targets and network providers operate under their own policies. Microsoft may process information associated with Store purchases, installation, updates, licensing or Windows diagnostics under the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement), independently of this application's local logging.

The public copy of this policy is hosted on GitHub Pages. Visiting that page sends normal web requests to GitHub, which may process technical information under the [GitHub General Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). The policy page contains no publisher-added analytics, advertising, external fonts or tracking scripts.

## 5. Exports, backups and sharing

Reports, project exports and database backups are written to locations you choose. They may contain target information, notes, observations and findings. A selected location may be a shared drive or a folder synchronized by another service; those services can copy the files according to their settings. Review exported files before sharing them. The application does not automatically email or upload these files.

## 6. Access, retention and deletion

You can view and edit your workspace in the application and export supported project or report data. Workspace records remain until you delete them. Deleting a project removes its related targets, scans, observations, findings and project activity; deleting a target removes its related scan history and findings. Archiving a project does not delete it.

To remove the entire local workspace, first locate it through **Settings → Open data folder**, close the application, and delete that workspace folder using Windows. Do not delete unrelated folders. Delete any exported reports, project files and backups separately wherever you saved them, including synchronized or shared copies. Uninstall behavior depends on installation type and Windows storage handling, so do not rely on uninstalling alone to remove custom workspaces or exported files. Database record deletion and ordinary file deletion are not secure erasure and may leave recoverable copies or backups.

## 7. Permissions

BugHunter Pro runs as a desktop application under your Windows user account and does not require administrator privileges for normal use. It needs access to its local workspace and files you choose to import, export or back up, plus network access when you initiate scans. The local demo opens a loopback listening socket. It does not request camera, microphone, contacts or location-service access. A Store package may identify this desktop execution model as full-trust; this does not mean the application automatically runs as administrator.

## 8. Contact and privacy requests

For support or privacy questions, contact **Aria Vision** at [sn.moosavi@gmail.com](mailto:sn.moosavi@gmail.com). Include “BugHunter Pro” in the subject. You decide what to include in your message; do not send passwords, access tokens or unnecessary scan evidence. Sending email discloses your address and message to the publisher and the email providers involved. The publisher cannot remotely access, retrieve or delete workspace files that remain on your device. Contact the publisher about information you have separately provided in correspondence and any applicable privacy rights.

## 9. Changes to this policy

Updates will be published on this page with a revised effective date and application version where applicable. The application includes a local copy for its shipped version. Material changes to application data practices will also be described in the relevant release notes or an in-app notice as appropriate. This version does not automatically download privacy-policy updates; review the public page for the current policy.

Official policy: https://snmoosavi.github.io/privacy-policy/bughunter-pro/
