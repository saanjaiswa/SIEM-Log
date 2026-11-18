Deployed Link :-   https://siem-log.netlify.app/
# LogSentinel SIEM — Network & Security Log Analyzer

An interactive, zero-backend Security Information & Event Management (SIEM) web application for ingesting, normalizing, detecting, and correlating security logs across **Linux Authentication**, **Windows Security Events**, **Web Servers (Nginx/Apache)**, and **Cloud Services (AWS CloudTrail)**.

## Features
1. **Multi-Source Log Ingestion**: Drag-and-drop `.log`, `.txt`, `.json`, `.csv`, `.jsonl` files, paste raw logs, or load built-in attack scenarios.
2. **Event Normalization**: Parses heterogeneous log formats into a unified searchable schema (`timestamp`, `source_type`, `event_action`, `outcome`, `severity`, `actor`, `src_ip`, `dst_host`, `resource`, `event_code`, `raw`).
3. **Automated Threat Detection**:
   - **Brute-Force Attempts**: Detects repeated authentication failures and flags brute-force followed by successful login (`T1110`).
   - **Unusual Logins**: Flags logins without MFA, off-hours external logins, and multi-IP concurrent access (`T1078`).
   - **Privilege Changes**: Detects `sudo` root escalation, `useradd`/`usermod`, Windows `4720`/`4732` admin group additions, and AWS `AttachUserPolicy`/`CreateAccessKey` (`T1098`).
   - **Suspicious Access Patterns**: Detects web SQLi/LFI/directory scanning (`T1190`), obfuscated PowerShell (`T1059.001`), and public S3/Security Group exposure (`T1562`).
4. **Incident Correlation**: Groups related alerts across platforms by shared IP, actor, and time window into chronological attack timelines with risk scores and analyst notes.
5. **Investigation & Export**: Full-text search, faceted filtering, slide-over raw log inspection drawer, alert status workflow, and JSON report export.

## Hosting Instructions (Free Static Platforms)
Because this application runs 100% client-side in the browser, you can host it in under 1 minute:
- **Vercel**: Run `npx vercel --prod` inside this folder, or drag-and-drop the folder on vercel.com.
- **Netlify**: Drag-and-drop this folder onto [app.netlify.com/drop](https://app.netlify.com/drop).
- **GitHub Pages**: Push this folder to a GitHub repository and enable **Settings → Pages → Deploy from branch (`main` / root)**.
