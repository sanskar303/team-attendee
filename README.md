# Team Attendee

*Simplify Work. Track Attendance. Empower Teams.*

A complete HR SaaS front end: landing page, login, employee self-service, and admin/HR/manager consoles with role-based access. Pure HTML/CSS/JS — no build step, works offline.

## Run it (30 seconds)
Open `www/index.html` in a browser, or run `npx serve www`.

Demo logins (password `demo123`):

| Role | Employee ID |
|---|---|
| Super Admin | TA-1001 |
| HR Admin | TA-1002 |
| Manager | TA-1003 |
| Employee | TA-1004 |

Data is stored in the browser (`localStorage`). *Help & Support → Reset demo data* restores the sample data.

## Get the Android APK
See **BUILD_APK.md**. Easiest route: push this folder to a GitHub repo — the included workflow builds `app-debug.apk` for you.

## Project layout
```
www/
  index.html            entry point
  css/styles.css        design system (navy #172554, blue #2563EB, teal #14B8A6)
  js/data.js            entities + sample data + async Store API  ← swap for real backend
  js/ui.js              icons, charts, tables, modals, toasts
  js/public.js          landing page + login
  js/app.js             shell, router, RBAC, employee pages
  js/admin.js           dashboard, employees, attendance, payroll, leave, reports, settings
  manifest.webmanifest, sw.js   installable PWA
capacitor.config.json   Android wrapper config
```

## Connecting a real backend
Every write goes through `Store.api(fn)` in `js/data.js`, which already simulates latency and is awaited by the UI (loading / success / error states exist). Replace its body with `fetch()` calls. Entities: companies, employees, users, roles, departments, designations, teams, attendance (check-in/out + hours), salaries, payroll, payslips, leave requests + balances, holidays, notifications, documents, reports, audit logs.

**Before production:** passwords in the demo are plain text and role checks run in the browser. A real deployment must hash passwords, enforce permissions on the server, and never ship salary data to unauthorised clients.
