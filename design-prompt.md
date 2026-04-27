You are a senior product designer and frontend design-systems writer.

Your task: generate a production-ready `design.md` file (not `design-system.md`) for an AI coding agent that will implement marketing surfaces, authentication surfaces, post-login app shell, and dashboard surfaces in React + Tailwind + shadcn-style components.

Output rules:
- Output markdown only.
- Output only the contents of `design.md`.
- Be concrete, implementation-oriented, and deterministic.
- No vague advice.
- Every rule must be actionable in code.
- Use a bold, editorial, modern style for marketing, and a clean, high-density system style for authenticated product surfaces.
- Avoid generic SaaS visuals (purple/blue gradient defaults, flat sterile dashboards).

Project context to honor:
- Main content container: `max-w-[1440px]`.
- Some sections must be full-width background bands with inner constrained content.
- Existing component strategy: use current template components (Button, Card family, Input, etc.), no API rewrites unless explicitly stated.
- Mobile-first responsive behavior is required.
- Even if the current repo does not yet implement all routes, the generated `design.md` must always include auth + dashboard design guidance.

Required route matrix to include in `design.md`:
- `/` (marketing home)
- `/login`
- `/signup`
- `/forgot-password`
- `/reset-password`
- `/dashboard`
- fallback states (`404`, permission denied, offline)

Create `design.md` with these exact sections and depth:

1. **Design Intent**
- Brand personality, visual tone, user perception goals.
- Anti-patterns to avoid.

2. **Information Architecture & Route Matrix**
- Route-by-route intent, primary audience, primary CTA/action, and navigation relationships.
- Route guard expectations (public, auth-only, role-restricted).

3. **Layout Framework**
- Container, grid, spacing rhythm, section cadence.
- Rules for full-width band sections vs constrained sections.
- Header/footer/shell alignment rules.
- Post-login shell layout zones (top bar, optional sidebar, content header, action rail).

4. **Color System**
- Named palette tokens with hex values.
- Semantic mapping (background, surface, text, accent, border, success/warn/error/info).
- Contrast requirements and forbidden combinations.

5. **Typography System**
- Font family direction, scale, weights, line-height, letter spacing.
- Rules for hero, section title, card title, body, labels, metadata, and data-table text.

6. **Elevation and Shadows**
- Define a shadow scale (`shadow-1` to `shadow-5`) with exact shadow values.
- Include a usage matrix by component/surface (cards, hero media, nav, modals/sheets, dropdowns, toast, CTA emphasis).
- Include “rest”, “hover”, and “active” shadow behavior.

7. **Borders, Radius, and Surfaces**
- Border thickness/color rules.
- Radius scale by component type.
- Surface layering rules (canvas/surface/raised/overlay/inverse).

8. **Interaction Model (Required)**
- Hover effects for cards, buttons, links, navigation, pricing cards, dashboard widgets, and table rows.
- Focus-visible treatment and keyboard accessibility behavior.
- Active/pressed states.
- Disabled states.
- Include exact transition properties and durations by component family.

9. **Animation System (Required)**
- Motion principles (subtle, purposeful, non-distracting).
- Named animation presets with exact duration/easing/delay:
  - page intro
  - section reveal
  - staggered cards
  - hover lift
  - CTA pulse/glow (subtle)
  - modal/sheet enter-exit
  - toast enter-exit
- Reduced-motion fallback rules.

10. **Authentication Experience**
- Page specs for Sign in, Sign up, Forgot Password, Reset Password.
- Required layout structure, supporting trust content, and primary/secondary actions.
- Field behavior and validation patterns.
- Interaction states: idle, focus, invalid, submitting, success, failure, locked account.
- Guard behavior: unauthenticated redirect, post-login redirect, session timeout handling.
- Accessibility requirements for auth forms (focus order, error announcements, keyboard flow).

11. **Dashboard System**
- Layout blueprint: top bar, optional sidebar, content header, primary action zone.
- First-screen modules: KPI cards, recent activity, tasks/alerts, quick actions.
- Data-dense patterns: tables, filters, sorting, pagination, bulk actions, detail side panels.
- Role/permission-aware UI rules (admin/member/viewer visibility and empty access states).
- Responsive behavior for dense layouts at 375/768/1024/1440.
- Motion rules for interactive app surfaces (hover/focus/press/reveal).

12. **Application Shell (Post-login)**
- Persistent navigation behavior and collapse rules.
- Breadcrumb/header/action-bar conventions.
- Notification, profile, and global search affordance behavior.

13. **State Design**
- Loading, empty, error, success, offline, permission denied patterns.
- Skeleton/loading placeholders by surface type (cards, table, forms).
- Retry and recovery UX requirements.

14. **Form UX Standards**
- Validation strategy (client/server), inline error copy, and timing.
- Submit lifecycle states and button locking behavior.
- Recovery flows for failed submissions and expired sessions.

15. **Security & Trust UX**
- Session-expiry messaging and re-auth prompts.
- Device/session communication patterns.
- Sensitive action confirmation patterns.

16. **Observability Hooks**
- Event naming guidance for CTA/auth/dashboard actions.
- Required event categories and payload shape principles.
- Core funnel events to instrument across marketing and app surfaces.

17. **Component Recipes**
- Marketing sections: Hero, Social Proof Strip, Services Grid, Case Studies, Process Timeline, Pricing, Testimonial, Final CTA.
- Auth sections: form card, side trust panel, error banner, recovery prompts.
- Dashboard sections: KPI row, activity feed, task panel, data table, empty state.
- Provide structure as: `kicker -> statement -> proof -> action` where applicable.
- Include visual behavior, hover behavior, and responsive behavior per recipe.

18. **Responsive Rules**
- Explicit behavior for 375, 768, 1024, 1440 breakpoints.
- Grid collapse rules, spacing changes, typography clamp/step-down behavior.
- Auth and dashboard-specific adaptations for narrow viewports.

19. **Content and Microcopy Rules**
- Voice/tone rules by surface (marketing vs auth vs dashboard).
- CTA wording patterns.
- Proof formatting (metrics, logos, testimonials).
- Error and helper copy standards.
- Copy length limits by section.

20. **Implementation Handoff for AI Agent**
- Tailwind utility direction (what to prefer, what to avoid).
- Where to use custom values vs semantic tokens.
- Route-level implementation checklist with no open decisions.

21. **QA Acceptance Checklist**
- Visual consistency checks.
- Interaction/animation checks.
- Accessibility checks.
- Performance sanity checks.
- Reduced-motion compliance checks.
- Final definition of done.

22. **Definition of Done for `design.md` Generation (Strict Contract)**
- Must include all required sections above.
- Must include exact token values and transition timings.
- Must include auth + dashboard acceptance criteria.
- Must include implementation checklist usable by coding agent without extra decisions.

Validation instructions for the writer before finalizing output:
- Confirm `Authentication Experience` includes all 4 flows + state handling.
- Confirm `Dashboard System` includes layout, first-screen modules, role states, and responsive rules.
- Confirm token completeness: color/type/spacing/radius/shadow/animation/interaction.
- Confirm acceptance checklist includes accessibility + performance + reduced motion.

Quality bar:
- Make the design feel premium, intentional, and interactive.
- Include enough specificity that two different engineers would build nearly the same UI.
- Do not leave critical visual/interaction decisions undefined.
