# Stitch Animated Frontend Interface — SQMS

Static, hand-designed screen exports for the **Student Query Management System (SQMS)**, generated with Stitch. Every screen is a self-contained `code.html` file (Tailwind via CDN, inline styles and scripts), so no build step, package manager or server is required.

Design language, palette, typography and status/priority tokens are documented in [`sqms_design_system.md`](./sqms_design_system.md).

## Open the screens locally

Quickest way — open the index page and click through everything:

1. Double-click [`index.html`](./index.html) (or run `start index.html` on Windows, `open index.html` on macOS).
2. Pick a screen from the list; each screen then lives at its own folder path.

You can also open a single screen directly, e.g. `student_my_queries_loaded/code.html`. Or serve the folder over HTTP if your browser restricts local file access:

```bash
python -m http.server 8000
# then visit http://127.0.0.1:8000/
```

All links between screens are plain relative paths, so they work from both `file://` and an HTTP server.

## Screens

### Public

| Folder | Screen | What it is for |
| --- | --- | --- |
| `public_login_default` | Sign In | Default sign-in form for students, staff and admins, with role entry point and error/validation states. |
| `public_student_registration_default` | Student Registration | Self-service student sign-up: account details, student ID, department and password creation. |

### Student

| Folder | Screen | What it is for |
| --- | --- | --- |
| `student_my_queries_loaded` | My Queries | A student's query history in a status-tagged table, with filters and the entry point for a new query. |
| `student_new_query_default` | New Query | Submission form for a new query: department/category, subject, description, priority and attachments. |
| `student_query_detail_active` | Query Detail (Q-2026-0142) | Read-only view of one submitted query: status timeline, staff replies and the student's own messages. |
| `student_edit_query_delete_modal` | Edit Query / Delete Modal (Q-2026-0129) | Editable version of a submitted query plus the confirmation modal for deleting it. |

### Staff

| Folder | Screen | What it is for |
| --- | --- | --- |
| `staff_home_default` | Staff Home | Department staff landing page: greeting, queue summary counts and recently assigned queries. |
| `staff_department_queue_filterable` | Department Queue | Filterable, sortable list of every query in a department queue (status, priority, assignee, date). |
| `staff_query_detail_two_column` | Staff Query Detail (Q-2026-0142) | Two-column working view: query thread on the left, status/priority/assignment controls and history on the right. |

### Admin

| Folder | Screen | What it is for |
| --- | --- | --- |
| `admin_dashboard_overview` | Admin Dashboard / System Overview | Institution-wide metrics: query volume, resolution time, department load and status breakdown. |
| `admin_all_queries_table` | All System Queries | Cross-department query table with search, filtering and drill-down into any query. |
| `admin_users_management` | Users Management | Directory of students, staff and admins with roles, departments and account actions. |
| `admin_departments_categories_crud` | Departments & Categories | Create/edit/delete departments and the query categories routed to them. |

### System

| Folder | Screen | What it is for |
| --- | --- | --- |
| `system_403_404_error_pages` | Access Denied (403 / 404) | Error state for unauthorised access and unknown routes, with a route back into the app. |
| `system_generic_error_page` | Generic Error | Fallback screen for failed or incomplete requests (server error) with retry guidance. |

## Repository layout

```
index.html                     # link hub for every screen
sqms_design_system.md          # palette, type, spacing and component tokens
<screen_folder>/code.html      # one self-contained screen per folder
```

## Notes

- These are static visual exports: there is no backend, no real authentication and no persistence. Form submissions and role-based routing are illustrative only.
- Fonts and the Tailwind runtime load from CDNs, so an internet connection is needed for the intended look.
