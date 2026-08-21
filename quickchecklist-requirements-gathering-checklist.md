## Pre-Call Preparation:

   * [ ] Research the client's industry, market position, and competitors

   * [ ] Identify the client's business objectives and goals

   * [ ] Review any available documentation, such as business plans, project proposals, or user requirements

   * [ ] Prepare a detailed list of questions to ask the client

   * [ ] Pull their current site/app: tech (CMS, auth, payments), obvious broken flows, and analytics if they will share

   * [ ] Know who signs invoices vs who will use the system daily (often different people)

## Introduction:

   * [ ] Introduce yourself and the project team members

   * [ ] Explain the purpose and objectives of the call

   * [ ] Confirm the availability of key stakeholders and decision-makers

   * [ ] Confirm recording/notes permission and where the write-up will live

## Project Scope:

   * [ ] Discuss the project scope, including the features, functionalities, and requirements of the software/application/system being developed

   * [ ] Clarify any ambiguous or unclear requirements

   * [ ] Identify any potential challenges or limitations of the project scope

   * [ ] Ask what they will still do in Excel/WhatsApp after go-live — that is hidden scope

   * [ ] Ask what they will not pay extra for even if they mentioned it (“nice AI dashboard”)

## Business Requirements:

   * [ ] Identify the business goals and objectives that the software/application/system is intended to achieve

   * [ ] Understand the business processes that the software/application/system is intended to automate or improve

   * [ ] Identify any regulatory or compliance requirements that must be met

   * [ ] Who is liable if data is wrong (tax, payroll, health) — that drives audit logs

   * [ ] Peak calendar: month-end, Diwali/Black Friday, exam week, harvest — capacity and freeze windows

## Technical Requirements:

   * [ ] Identify the technical requirements of the software/application/system, such as hardware, software, and networking infrastructure

   * [ ] Identify any specific programming languages, frameworks, or platforms that must be used

   * [ ] Discuss any integration requirements with existing systems or third-party applications

   * [ ] Data residency (IN/EU/US), who owns the cloud account, and who holds production credentials after handover

   * [ ] SSO/LDAP/WhatsApp/SMS vendor they already pay for vs greenfield

   * [ ] Offline, poor network, and shared-device (shop floor / kiosk) needs

## User Requirements:

   * [ ] Identify the end-users of the software/application/system and their needs

   * [ ] Discuss the user experience and user interface requirements

   * [ ] Identify any accessibility or usability requirements

   * [ ] Languages, literacy, and whether they will train users or expect zero training

   * [ ] Roles: who may see PII, export, refund, delete — names not “admin vs user” only

## Functional Requirements:

   * [ ] Identify the specific functionalities that the software/application/system must provide

   * [ ] Identify any specific business logic or algorithms that must be implemented

   * [ ] Discuss any security or authentication requirements

   * [ ] Notifications: email vs SMS vs WhatsApp vs in-app; who pays the SMS bill

   * [ ] Reports they currently email to a board — field-by-field, not “analytics”

   * [ ] Idempotency: double payment, double ticket, webhook retries

## Non-Functional Requirements:

   * [ ] Identify any performance or scalability requirements (numbers: users, RPS, record counts, file sizes)

   * [ ] Discuss any reliability or availability requirements (hours of operation, RPO/RTO, backup owner)

   * [ ] Identify any legal or contractual requirements that must be met

   * [ ] Browser/OS/device list they will actually support (including “only Chrome on Windows 7” if that is reality)

   * [ ] Accessibility bar (WCAG 2.2 A/AA) if they sell to government/education

## Acceptance Criteria:

   * [ ] Identify the acceptance criteria for the software/application/system

   * [ ] Define the test cases that will be used to validate the software/application/system

   * [ ] Discuss any performance metrics or benchmarks that must be achieved

   * [ ] Name the human who will UAT-sign, and what environment they will use

   * [ ] Definition of done includes data migration quality (spot-check N records), not only features

## Project Timeline:

   * [ ] Discuss the project timeline, including milestones and deadlines

   * [ ] Identify any risks or constraints that may impact the timeline

   * [ ] Discuss the communication and reporting requirements for the project

   * [ ] External dates: store review, legal, client’s board, domain/DNS access delays

   * [ ] Who is on PTO in the critical two weeks

## Success Metrics:

   * [ ] Agree how success will be measured after launch (KPIs, conversion, time saved, error rate)

   * [ ] Confirm who owns reporting and how often results will be reviewed

   * [ ] Capture out-of-scope items so they do not silently enter the first release

   * [ ] Baseline: today’s time-to-complete or error rate, or you cannot claim improvement

## Money and Commercial (ask, even if PM “doesn’t do commercials”):

   * [ ] Licenses they must buy (maps, SMS, Apple developer, SSL, WhatsApp Business)

   * [ ] Change request path when a director adds a module in week 6

   * [ ] Support hours after launch (email-only vs 24h) and who is on-call

## Post-Call Follow-Up:

   * [ ] Summarize the key points discussed during the call and share it with the client for their review and confirmation

   * [ ] Identify any follow-up actions, such as additional meetings or information gathering

   * [ ] Provide a clear next steps and timeline for the project

   * [ ] Share a written requirements summary and ask the client to confirm in writing

   * [ ] List open questions as a numbered list they can reply to inline — not a paragraph
