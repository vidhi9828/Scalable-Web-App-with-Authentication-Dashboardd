# Design Guidelines: Authentication & Task Management Dashboard

## Design Approach
**Selected Framework:** Design System Approach inspired by Linear and Notion
**Rationale:** Utility-focused productivity application requiring clean, efficient information architecture with standard UI patterns optimized for task management and data display.

## Typography System

**Font Family:** Inter (Google Fonts)
- Primary: Inter for all UI elements
- Monospace: JetBrains Mono for code/technical displays

**Hierarchy:**
- Page Titles: text-3xl font-semibold
- Section Headers: text-xl font-semibold
- Card Titles: text-lg font-medium
- Body Text: text-base font-normal
- Labels: text-sm font-medium
- Helper Text: text-sm font-normal
- Captions: text-xs font-normal

## Layout & Spacing System

**Spacing Scale:** Use Tailwind units of 2, 4, 6, 8, 12, 16, 24
- Component padding: p-4 to p-6
- Section spacing: space-y-6 to space-y-8
- Card gaps: gap-4 to gap-6
- Form field spacing: space-y-4

**Container Strategy:**
- Auth pages: max-w-md centered
- Dashboard: Full-width with max-w-7xl for content
- Forms: max-w-2xl
- Cards: Responsive grid (grid-cols-1 md:grid-cols-2 lg:grid-cols-3)

## Component Library

### Authentication Pages (Login/Register)

**Layout:**
- Split-screen design: Left 40% for form, Right 60% for branded visual
- Form container: Centered card with shadow, p-8, max-w-md
- Visual side: Full-height gradient or abstract illustration
- Logo placement: Top-left of form container
- Social proof element below form: "Trusted by 500+ users" with small avatars

**Form Structure:**
- Input fields: Full-width, h-12, rounded-lg, border focus ring
- Label above input: text-sm font-medium, mb-2
- Error messages: text-sm below input, mt-1
- Primary CTA: Full-width, h-12, rounded-lg, font-semibold
- Secondary link: Centered below CTA, text-sm
- Password field: Include show/hide toggle icon

### Dashboard Layout

**Navigation:**
- Sidebar: Fixed left, w-64, full-height
  - Logo at top (p-6)
  - Navigation items: p-3, rounded-lg, with icons from Heroicons
  - User profile at bottom: Avatar + name + logout button
- Top bar: h-16, border-b
  - Page title on left
  - Search bar in center (max-w-md)
  - Notifications + user menu on right

**Main Content Area:**
- Header section: mb-8
  - Page title + description
  - Action buttons aligned right
- Content grid: gap-6
- Empty states: Centered with icon, text, and CTA

### Task/CRUD Components

**Task Cards:**
- Border, rounded-lg, p-4
- Header row: Title + status badge + actions menu
- Meta row: Due date, assignee avatar, priority indicator
- Description: text-sm, truncated with "Read more"
- Footer: Created date + edit/delete icons

**Data Table (Alternative view):**
- Sticky header: bg with border-b
- Row height: h-16, hover state
- Columns: Checkbox, Title, Status, Priority, Due Date, Actions
- Pagination: Bottom right

**Filter/Search Panel:**
- Horizontal filter bar above content
- Search input: w-64 to w-96
- Filter dropdowns: Status, Priority, Date range
- Clear filters button
- Results count: "Showing X of Y tasks"

### Forms (Create/Edit Task)

**Modal or Side Panel:**
- Modal: max-w-2xl, p-6, shadow-xl
- Fields layout: 2-column for short fields, 1-column for textarea
- Required field indicator: Red asterisk
- Field groups: space-y-4
- Action buttons: Right-aligned, gap-2 (Cancel + Save)

**Form Fields:**
- Text inputs: h-12, rounded-lg
- Textareas: min-h-32, rounded-lg
- Select dropdowns: h-12, rounded-lg, chevron icon
- Date pickers: h-12, calendar icon
- Toggle switches: For boolean options

### Profile Page

**Layout:**
- Header section: Avatar (large, 24), Name, Email, Edit button
- Tabs: Profile, Settings, Security
- Content cards: Organized by category
- Form fields: Similar to task forms
- Save changes: Sticky bottom bar with save button

## Icons
**Library:** Heroicons (via CDN)
- Navigation: outline icons
- Actions: solid icons for primary, outline for secondary
- Status indicators: Solid filled icons

## Images

**Authentication Pages:**
- Large branded visual/illustration on right side of split-screen (60% width)
- Abstract, modern illustration representing productivity/collaboration
- Subtle gradient overlay for depth

**Dashboard:**
- User avatars: Circular, various sizes (8, 10, 12, 16, 24)
- Empty state illustrations: Centered, max-w-sm
- Profile page: Large avatar upload area

**Note:** No large hero image needed for dashboard interface. Focus on clean, functional layouts.

## Accessibility & States

**Focus States:**
- Ring-2 with offset for all interactive elements
- Clear focus indicators on all form fields

**Loading States:**
- Skeleton screens for data tables and cards
- Spinner for button actions
- Progress bar for multi-step processes

**Interactive States:**
- Hover: Slight scale or background change
- Active: Pressed state with reduced scale
- Disabled: Reduced opacity (0.5)

## Responsive Behavior

**Breakpoints:**
- Mobile: Single column, hidden sidebar (hamburger menu)
- Tablet (md): 2-column grids, collapsible sidebar
- Desktop (lg): 3-column grids, fixed sidebar

**Mobile Optimizations:**
- Bottom navigation bar replaces sidebar
- Full-screen modals instead of centered
- Stacked form layouts
- Simplified table views (card-based)

## Animation Principles

**Minimal, purposeful animations:**
- Page transitions: Fade in
- Modal/dropdown: Scale and fade (100ms)
- Success feedback: Checkmark animation
- No decorative or scroll-triggered animations