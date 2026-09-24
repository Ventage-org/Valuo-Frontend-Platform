---
name: ValuaProp Precision
colors:
  surface: '#f8f9ff'
  surface-dim: '#cbdbf5'
  surface-bright: '#f8f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#eff4ff'
  surface-container: '#e5eeff'
  surface-container-high: '#dce9ff'
  surface-container-highest: '#d3e4fe'
  on-surface: '#0b1c30'
  on-surface-variant: '#434655'
  inverse-surface: '#213145'
  inverse-on-surface: '#eaf1ff'
  outline: '#737686'
  outline-variant: '#c3c6d7'
  surface-tint: '#0053db'
  primary: '#004ac6'
  on-primary: '#ffffff'
  primary-container: '#2563eb'
  on-primary-container: '#eeefff'
  inverse-primary: '#b4c5ff'
  secondary: '#565e74'
  on-secondary: '#ffffff'
  secondary-container: '#dae2fd'
  on-secondary-container: '#5c647a'
  tertiary: '#006242'
  on-tertiary: '#ffffff'
  tertiary-container: '#007d55'
  on-tertiary-container: '#bdffdb'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#dbe1ff'
  primary-fixed-dim: '#b4c5ff'
  on-primary-fixed: '#00174b'
  on-primary-fixed-variant: '#003ea8'
  secondary-fixed: '#dae2fd'
  secondary-fixed-dim: '#bec6e0'
  on-secondary-fixed: '#131b2e'
  on-secondary-fixed-variant: '#3f465c'
  tertiary-fixed: '#6ffbbe'
  tertiary-fixed-dim: '#4edea3'
  on-tertiary-fixed: '#002113'
  on-tertiary-fixed-variant: '#005236'
  background: '#f8f9ff'
  on-background: '#0b1c30'
  surface-variant: '#d3e4fe'
typography:
  display-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 2.25rem
    fontWeight: '700'
    lineHeight: 2.75rem
    letterSpacing: -0.025em
  display-lg-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 1.75rem
    fontWeight: '700'
    lineHeight: 2.25rem
    letterSpacing: -0.02em
  headline-xl:
    fontFamily: Plus Jakarta Sans
    fontSize: 1.875rem
    fontWeight: '600'
    lineHeight: 2.25rem
    letterSpacing: -0.02em
  headline-xl-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 1.5rem
    fontWeight: '600'
    lineHeight: 2rem
    letterSpacing: -0.015em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 1.5rem
    fontWeight: '600'
    lineHeight: 2rem
    letterSpacing: -0.015em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 1.25rem
    fontWeight: '600'
    lineHeight: 1.75rem
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 1.125rem
    fontWeight: '600'
    lineHeight: 1.5rem
    letterSpacing: -0.005em
  title-md:
    fontFamily: Inter
    fontSize: 1rem
    fontWeight: '600'
    lineHeight: 1.5rem
  body-lg:
    fontFamily: Inter
    fontSize: 1.125rem
    fontWeight: '400'
    lineHeight: 1.75rem
  body-md:
    fontFamily: Inter
    fontSize: 0.875rem
    fontWeight: '400'
    lineHeight: 1.375rem
  body-sm:
    fontFamily: Inter
    fontSize: 0.75rem
    fontWeight: '400'
    lineHeight: 1.125rem
  data-metric:
    fontFamily: Inter
    fontSize: 1.5rem
    fontWeight: '600'
    lineHeight: 2rem
    letterSpacing: -0.01em
  label-md:
    fontFamily: Inter
    fontSize: 0.875rem
    fontWeight: '500'
    lineHeight: 1.25rem
  label-sm:
    fontFamily: Inter
    fontSize: 0.75rem
    fontWeight: '500'
    lineHeight: 1rem
    letterSpacing: 0.025em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  space-2xs: 0.25rem
  space-xs: 0.5rem
  space-sm: 0.75rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2rem
  space-2xl: 3rem
  space-3xl: 4rem
  gutter-mobile: 1rem
  gutter-desktop: 1.5rem
  margin-mobile: 1rem
  margin-tablet: 1.5rem
  margin-desktop: 2rem
  max-width-content: 88rem
---

## Brand & Style

The design system establishes an institutional-grade, predictive intelligence aesthetic for enterprise real estate analytics and algorithmic property appraisal. It balances statistical rigor with executive clarity, projecting unimpeachable data fidelity, predictability, and fiduciary security. 

Designed for portfolio asset managers, underwriting teams, and quantitative real estate analysts, the visual mood rejects frivolous ornamentation in favor of high-density clarity and modern enterprise polish. Interfaces rely on structured geometric hierarchy, calm balanced contrast, and surgical analytical feedback. Visual weight is used systematically to distinguish ground-truth financial records from probabilistic machine-learning forecasts.

## Colors

The color architecture is built around calibrated precision and financial significance:

- **Primary (`#2563EB`)**: Anchor operational blue representing interactive workflows, focused selection states, predictive convergence indicators, and high-priority actions.
- **Secondary (`#0F172A`)**: Deep obsidian slate delivering stable structural contrast for key navigation bars, high-level KPIs, and deep structural surfaces.
- **Tertiary (`#10B981` / `#059669`)**: Emerald yield used selectively for positive feature attribution (positive SHAP values), model confidence scores, and value premiums.
- **Negative Impact Accent (`#F43F5E`)**: Rich coral rose reserved for risk depreciation, negative predictive vectors, downside variance, and validation alerts.
- **Neutral Palette**: Tinted slate-gray gradations (`#F8FAFC` canvas, `#FFFFFF` containers, `#E2E8F0` structural delineations, and `#64748B` supporting copy) that prevent glare during long analytical sessions while maintaining clean separation.

## Typography

Typography unifies structural confidence with analytical precision. Headings rendered in **Plus Jakarta Sans** establish an authoritative, modern corporate tone with geometric clarity. All operational data points, tables, dashboard widgets, and continuous body text rely on **Inter**.

To ensure total alignment across financial valuations, confidence intervals, and SHAP delta metrics, all numerical interfaces must enforce tabular figures (`font-variant-numeric: tabular-nums; font-feature-settings: "tnum" 1, "cv05" 1`). Labels and micro-badges use tight line heights with refined kerning to maximize scanning efficiency in dense multi-metric dashboards.

## Layout & Spacing

The layout is engineered using an 8pt base grid with an inner 4pt sub-grid for compact data density. The structural model employs a fluid 12-column system constrained to a maximum content width of 1408px (`88rem`), accommodating split-pane analytical views, dynamic side panels, and variable-length property asset lists.

- **Breakpoints**:
  - `Mobile` (&lt; 768px): Single column, sticky macro KPI ribbon, full-bleed scrollable metrics.
  - `Tablet` (768px – 1024px): 8-column layout, collateral parameter sidebars collapsible into layered sheets.
  - `Desktop` (&gt; 1024px): 12-column layout with 24px gutters, fixed-width analytical query controls (320px–360px), and flexible multi-tile model insight arrays.

## Elevation & Depth

Visual hierarchy prioritizes surface purity and crisp boundary control over heavy physical drop shadows. The design system uses a combination of delicate borders (`1px solid #E2E8F0`) and ambient, low-opacity slate shadow diffusion:

- **Level 0 (Base Canvas)**: Flat `#F8FAFC`, non-elevated ground plane.
- **Level 1 (Card & Module Containers)**: Pure `#FFFFFF` background with `1px solid #E2E8F0` border and subtle ambient shadow: `0 1px 3px 0 rgba(15, 23, 42, 0.04), 0 1px 2px -1px rgba(15, 23, 42, 0.04)`.
- **Level 2 (Interactive Elements & Dropdowns)**: Elevated menus, popovers, and hovered property rows: `0 4px 6px -1px rgba(15, 23, 42, 0.06), 0 2px 4px -2px rgba(15, 23, 42, 0.05)` with `#CBD5E1` border tint.
- **Level 3 (Overlays & Property Inspection Modals)**: Floating dialogs and comparative scenario sheets: `0 20px 25px -5px rgba(15, 23, 42, 0.08), 0 8px 10px -6px rgba(15, 23, 42, 0.04)`.

## Shapes

The design system adopts roundedness level `2`, balancing modern humanized software appeal with structured institutional utility:

- Default base elements (interactive input fields, utility tags, segmented items, buttons) leverage `rounded` (8px / `0.5rem`).
- Cards, property appraisal summaries, and data visualization modules employ `rounded-lg` (16px / `1rem`).
- Large analytical modals, model training drawers, and top-tier valuation comparison panels utilize `rounded-xl` (24px / `1.5rem`).
- Circular geometry is strictly reserved for quantitative status indicators, user avatars, and categorical point-marker map pins.

## Components

### Buttons
- **Primary**: Solid `#2563EB` fill, white text, 8px radius, height 40px (desktop) / 44px (mobile), subtle hover darkening to `#1D4ED8`. Focus rings leverage `box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.2)`.
- **Secondary**: `#FFFFFF` background, `1px solid #E2E8F0` border, `#0F172A` label, transitioning to `#F1F5F9` on hover.
- **Destructive**: Tinted surface `#FFF1F2` with `#F43F5E` text and border for critical actions.

### Cards & Model Modules
- Encased in `rounded-lg` (16px) with pure white fill and `#E2E8F0` boundary lines. Section headers feature clear typography pairings, contextual tooltips explaining machine-learning confidence intervals, and compact action anchors.

### Input Fields & Interactive Sliders
- **Inputs**: Form fields feature `#F8FAFC` base fill, transitioning to `#FFFFFF` on active input, capped with a 1px border (`#CBD5E1`). Focus triggers an explicit `#2563EB` ring. Numeric inputs always render tabular figures.
- **Parameter Sliders (e.g., Square Footage, Interest Adjustments)**: 6px track height in `#E2E8F0` with dynamic `#2563EB` fill progress and a distinct 20px circular white thumb with a solid 2px primary border.

### Data Badges & Segmented Controls
- **Segmented Controls**: Embedded in an enclosed `#F1F5F9` track with an 8px radius. Active pill is `#FFFFFF` with a crisp micro-shadow and `#0F172A` text.
- **Badges**: 6px padding with 4px radius; positive model delta badges use `#ECFDF5` fill with `#059669` text; negative variance indicators use `#FFF1F2` fill with `#E11D48` text.

### Machine Learning Explanability (SHAP & Waterfall Bars)
- **Positive SHAP Contribution**: Rounded 4px horizontal bar segments rendered in `#10B981` with a semi-transparent hover envelope (`rgba(16, 185, 129, 0.15)`).
- **Negative SHAP Contribution**: Rounded 4px horizontal bar segments rendered in `#F43F5E` with an associated tooltip detailing baseline reference impact.
- **Baseline Origin Axis**: Crisp 1px dashed guide in `#94A3B8` establishing the base market median from which local predictions deviate.

### Lists & Key Metric Tables
- Striped data rows with subtle hover states (`#F8FAFC`), right-aligned numeric metrics in tabular Inter, and left-aligned categorical property metadata with low-contrast slate sub-labels.