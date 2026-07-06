# Idea-files
Great — let's scope the AI-powered Meeting Management System with your top differentiators: AI minutes + action item extraction, meeting necessity scorer, escalation engine, and meeting health dashboard, backed by Oracle DB.
Tech stack (matches your internship stack)
Frontend: React (space-navy aesthetic, like your Code Judge platform)
Backend: Java (Spring Boot) or Python (Flask/FastAPI) — your call
Database: Oracle
AI: Anthropic API (Claude) for summarization/extraction
Core data model (Oracle tables)
EMPLOYEES (id, name, email, role, manager_id)
MEETINGS (id, title, organizer_id, start_time, end_time, status, cost_estimate)
ATTENDEES (meeting_id, employee_id, attended, speaking_time)
AGENDA_ITEMS (id, meeting_id, topic, linked_meeting_id — for dependency tracking)
ACTION_ITEMS (id, meeting_id, description, owner_id, due_date, status, escalation_count)
MINUTES (meeting_id, raw_transcript, ai_summary, generated_at)
Build phases
Core CRUD — create/schedule meetings, add attendees, basic agenda (foundation, 20% of effort)
AI minutes engine — upload transcript/notes → Claude API extracts summary + action items + owners + due dates → auto-populates ACTION_ITEMS and MINUTES tables
Necessity scorer — small form (goal, decision needed?, attendee count) → Claude scores 1–10 with reasoning before allowing scheduling
Escalation engine — scheduled job checks overdue action items, increments escalation_count, notifies manager via email/in-app after 2 misses
Health dashboard — React charts (recharts) showing avg meeting length, on-time rate, action-item completion %, cost heatmap by team
Suggested order to build: Core CRUD → AI minutes engine (biggest wow-factor) → dashboard (visual payoff) → necessity scorer → escalation engine (polish last, since it depends on action items already working).
Want me to start scaffolding the React frontend now, or set up the Oracle schema/backend first?
