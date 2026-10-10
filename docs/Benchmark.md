# Benchmark Overview

The image below summarizes what we aim to increase, include, decrease, or remove when designing H2Organize. The platform analyses that follow explain the observations behind these decisions.

![H2Organize Benchmark](images/benchmark/H2Organize.png)

# 1\. Sistema APR (Direct Competitor)

## 1.1 Selection Rationale

“Sistema APR” was selected as the primary direct competitor because it is a Chilean SaaS platform designed specifically for Rural Drinking Water (APR / SSR) committees and cooperatives. It addresses the core operational cycle of customer management, meter reading logging, and billing collection, serving as a direct benchmark for the current UI standards and operational practices within the rural sanitation domain.

## 1.2 Mandatory Baseline Dimensions

**Technical Identification:**
    
- Name: Sistema APR  
- Platform: Responsive Web Application  
- Version Analyzed: Active Cloud Web Environment, Free Trial  
- Analysis Date: October 2026  
- Official Website: [https\://sistemaapr.cl/](https://sistemaapr.cl/)

![][image1]

**Target user profile:** Community operator, administrative secretaries and board members of Rural Sanitation Services (SSR) in Chile, seeking to digitize monthly meter logging, billing, and accounting workflows.

**Value Proposition:** An all-in-one cloud platform aimed at automating billing, water consumption recording and administrative tracking for rural water committees under a monthly subscription model.

**Core Functionalities:**

1. Member Registry: Creating, editing and monitoring the active operational status of community clients.  
2. Meter Reading Management: Individual and bulk entry of the monthly meter readings (cubic meters) with automated delta consumption calculations against previous records.  
3. Billing and Invoicing: Monthly invoice generation, tracking payment states (paid, pending, overdue), and integration with Chilean electronic invoicing (DTE/SII).  
4. Secondary administrative Modules: Outage logging, water infrastructure incident tracking, human resources (payroll and leave), warehouse inventory and internal accounting.

**Onboarding Flow:** Entry via an online registration form for a free trial. The system includes an initial step-by-step walkthrough, but it is extremely basic and limited to read-only views (overview tables and dashboards). It lacks contextual onboarding, tooltips, or field-level guidance during critical transactional workflows, such as creating or editing records (leaving users without support during data entry)

**Navigation Patterns:** Fixed left vertical sidebar combined with a top navigation bar. While the sidebar structure is two levels deep (modules and submodules), all the sections are rendered continuously in a flat list with over 40 current links, requiring extensive vertical scrolling.

**Visual Design and Consistency:** Generic administrative dashboard visual hierarchy. Uses a solid purple top header bar over light backgrounds, clean white table containers, and semantic accent color for status tags (green for active/paid), yellow for pending, red for overdue). Inconsistencies appear in action density: prominent text buttons sit next to congested clusters of micro-icons lacking descriptive text labels.

**Observable Accessibility:**

- Adequate color contrast on major metric cards and primary table headers.  
- Severe touch target deficiencies: action buttons inside tables measure approximately 24x24 px, falling below WCAG recommendations (minimum 44x44 px for touch interfaces)   
- Absence of explicit text labels on action buttons and lack of high-contrast modes for field work under direct sunlight

## 1.3 Annotated Visual Evidence

**Screenshot 1:** Member directory and operational Actions Overview  
![][image2]

1. **Area for improvement:** The sidebar exposes a lengthy vertical list without collapsible groupings, causing excessive cognitive load and slowing down access to high priority workflows (Heuristic: Aesthetic & minimalist design).  
2. **Area for improvement:** “Sector” and “Dirección” are redundant, unconstrained free-text inputs without validation or formatting guidance, if omitted, “Sector” renders an ambiguous “N/A” badge that looks interactive (Heuristic: Match between system and real world).  
3. **Highlight:** Primary call-to-action buttons ("+ Nuevo Socio" and "Ayuda") are permanently positioned in the upper right header with high contrast, enabling rapid execution of frequent tasks (Heuristic: Flexibility and efficiency of use).  
4. **Area for improvement:** Densely grouped micro-action buttons without text labels increase the likelihood of accidental click on touchscreens and mobile devices (Heuristic: Recognition rather than recall / WCAG touch target standards)

**Screenshot 2:** Monthly Meter Reading and Usage Records  
![][image3]

5. **Area for improvement:** The filter uses an unconstrained text input for the billing month (which should be a structured date picker for month and year) and static dropdown for members (which lacks search/autocomplete and will collapse with large datasets), increasing input errors (Heuristic: Error prevention / Flexibility and Efficiency).  
6. **Area for improvement:** Both the billing period ("Mes") and the specific inspection date are separated into two redundant columns, taking up valuable horizontal table space (Heuristic: Aesthetic and minimalist design).  
7. **Area for Improvement:** Miniature table action icons without labels or sufficient spacing increase interaction errors when operating on tablets or smartphones in the field (Heuristic: Error prevention / WCAG Touch Target Size).   
8. **Highlight:** Features a "Registro Masivo" option alongside single reading creation, letting field personnel paste or import batched route sheets rather than handling records one by one (Heuristic: Flexibility and efficiency of use). 

**Screenshot 3:** Billing Operations, Financial Metrics and filtering  
![][image4]

9. **Area for Improvement:** Selection checkboxes lack a header label and an associated batch-action toolbar, leaving the user uninformed about what action gets triggered upon selection (Heuristic: Visibility of system status).  
10. **Area for Improvement:** Contains an unlabelled blank text input without placeholder text, alongside an unpaginated dropdown selector that will experience cognitive and performance bottlenecks once scaled to hundreds of community members (Heuristics: Error prevention and Match between system and the real world).   
11. **Highlight:** Summary metric cards (KPIs) with color-coded status chips provide instant visibility into pending balances, total revenue, and overall financial health (Heuristic: Visibility of system status).  
12. **Area for Improvement:** "Generar Boletas" and "+ Nueva Boleta" coexist side-by-side without clear distinction between batch generation and single manual creation (Heuristic: Consistency and standards).   
13. **Area for Improvement:** A crowded row of five micro-icons without text descriptions introduces severe risk of triggering destructive actions (such as the trash can) due to lacking explicit labels and confirmation barriers (Heuristic: Recognition rather than recall / WCAG accessibility guidelines). 

# 2\. ComunidadFeliz (Analog Competitor)

## 2.1 Selection Rationale

“ComunidadFeliz” was selected as the primary analogous competitor because it is a leading property and community management SaaS platform in Latin America (primarily Chile). Although engineered for residential buildings and condominiums rather than rural water committees, it addresses the exact same underlying operational challenge: recurring community quota collection, tenant/unit registries, utility meter logging (internal sub-meters for water and electricity), and transparent financial reporting. Evaluating its UX patterns provides mature benchmarks for handling recurring debt tracking and shared resource billing in a community setting.

## 2.2 Mandatory Baseline Dimensions

**Technical Identification:**

- Name: ComunidadFeliz  
- Platform: Responsive web application and Mobile Apps (iOS and Android)  
- Version Analyzed: Active cloud web demo environment (preloaded sandbox data)  
- Analysis Date: October 2026  
- Official Website: [https\://www\.comunidadfeliz.cl/](https://www.comunidadfeliz.cl/) 

![][image5]

**Target User Profile:** Building administrators, community treasures, condominium committees, property managers handling collective finances, recurring charges and resident communications.

**Value Proposition:** An integrated cloud platform designed to automate common expense calculations, record sub-meter consumption, track overdue balances and streamline online payments to enhance financial transparency across residential communities.

**Core Functionalities:**

1. Unit and Resident Directory: Managing apartment or parcel ownership, tenant contact information, active occupancy states and emergency profiles.  
2. Sub-Meter Reading Module: Dedicated utility consumption tracking (water and/or electricity) featuring prior versus current index logging and automatic differential cost computation.  
3. Common Expense Billing and Debt Management: Automated monthly expense calculation, surcharge or penalty rules for arrears, digital invoicing and online payment gateway integration.  
4. Administrative and Financial Bookkeeping: Bank account reconciliation, income or expense ledgers, maintenance ticket management and community voting/announcements.

**Onboarding Flow:** Entry into the demo environment provides preloaded sample community data (units, expenses and transaction logs), allowing immediate contextual exploration without empty-state friction. The interface incorporates guided contextual banners, interactive pop-ups explaining key workflows across main views and a “AcademiaFeliz” where people learn how to use the website more efficiently.

**Navigation Patterns:** Structured layout featuring a persistent, collapsible left-hand sidebar paired with a top utility bar (community selector, notifications, profile). Navigation items are organized logically into categorized modules (Finances, Administration, Community) with clear visual hierarchy, avoiding vertical clutter.

**Visual Design and Consistency:** Polished corporate SaaS design system with a clean visual identity (balanced use of white space, subtle cards, and defined brand accents). Employs consistent semantic color-coding across tables and KPI summary cards (green for paid/surplus, red for arrears, neutral badges for status). High consistency in button hierarchy, standardizing primary versus secondary action buttons with legible typography and descriptive text labels.

**Observable Accessibility:**

- Strong text-to-background contrast across core tables, KPI cards, and navigational links.  
- Adequate touch target sizing for primary desktop and tablet interactive elements (well-spaced buttons meeting standard accessibility benchmarks).  
- Includes descriptive tooltips and icon-plus-text labels on critical interactive triggers, reducing ambiguity for non-expert users.  
- 

## 2.3 Annotated Visual Evidence

**Screenshot 1:** Utility logging and Consumption controls  
**![][image6]**

1. **Highlight:** The collapsed navigation rail auto-expands on hover, optimizing horizontal screen real estate for dense data tables while keeping full textual labels accessible without requiring explicit toggle clicks (Heuristic: Flexibility and efficiency of use).  
2. **Area for Improvement:** Persistent contextual alert banners warn operators about recalculation risks and pending notifications (Visibility of system status); however, stacking multiple full-width warning boxes introduces visual clutter and risks banner blindness (Heuristic: Aesthetic and minimalist design).  
3. **Highlight:** Features structured dropdown selectors for the billing month, year, utility type, and property units with a dedicated "Buscar" trigger, eliminating syntax errors from unconstrained free-text fields (Heuristic: Error prevention / Consistency and standards).  
4. **Highlight:** Integrates an automated "Alarmas de sobreconsumo" notification badge that flags atypical usage spikes before billing, preventing data-entry slip-ups and erroneous charge generation (Heuristic: Error prevention).  
5. **Highlight:** Floating persistent support widgets ("Asistente con IA" / "Chat con FelizIA") provide immediate, inline documentation and customer support without forcing users to abandon the active transactional view (Heuristic: Help and documentation).

**Screenshot 2:** Financial Overview, Collections and Account Receivables  
**![][image7]**

6. **Highlight:** Clearly separates primary transactional triggers (high-contrast "+ Nuevo Pago") from query parameters, using structured dropdowns and contextual input placeholders ("Ej: A201") to guide filtering (Heuristic: Flexibility and efficiency of use / Error prevention).  
7. **Highlight:** Summary metric cards (KPIs) offer immediate visibility into total billing, collected revenue, and outstanding community debt, minimizing the cognitive effort required to assess overall liquidity (Heuristic: Visibility of system status).  
8. **Area for Improvement:** Displays credit balances in green with a negative sign ("-\$..."), a financial convention that requires accounting literacy and may confuse non-expert community treasurers (Heuristic: Match between system and the real world).  
9. **Area for Improvement:** In-row action buttons rely strictly on miniature iconography (view, download, overflow menu) without text labels or sufficient tap-target spacing, increasing interaction slips on touchscreen devices (Heuristic: Recognition rather than recall / WCAG touch target standards).

**Screenshot 3:** Batch Billing Finalization, Surcharges and Proration Ledger  
**![][image8]**

10. **Highlight:** Groups maintenance routines ("Histórico de gastos comunes", "Editar mensaje de boleta") and manual overrides ("Forzar recálculo") in a dedicated top-right action bar, keeping utility commands accessible without competing with primary billing triggers (Heuristic: Flexibility and efficiency of use).  
11. **Area for Improvement:** The irreversible batch execution button ("Finalizar gastos comunes") sits adjacent to basic search parameters and features a structured date picker, but lacks prominent visual friction or explicit confirmation barriers to prevent accidental triggers (Heuristic: Error prevention).  
12. **Highlight:** Directly embeds contextual assistance links explaining complex calculations ("Revisa aquí cómo funciona el sistema de interés") right next to export actions (PDF/Excel), assisting users in validating financial rules without leaving the workflow (Heuristic: Help and documentation).  
13. **Area for Improvement:** The main ledger displays over 14 tightly packed financial columns ("Pror. Torre", "Capital atrasado", "Intereses y multas", etc.), causing severe visual fatigue and increasing the risk of reading alignment errors across long data rows (Heuristic: Aesthetic and minimalist design).

# 3\. Banco Falabella (Design Reference)

## 3.1 Selection Rationale

"Banco Falabella" (Chile) was selected as the design and interaction reference benchmark. While operating within the financial and retail banking sector rather than community utility management, mobile banking apps represent the gold standard for high-stakes transaction clarity, recurring debt settlements, and non-expert mobile interactions. Evaluating Banco Falabella provides proven UX patterns for transparent billing summaries, streamlined payment selection cards, and reassuring multi-channel security alerts that can be directly adapted to rural water bill consultations and payments.

## 3.2 Mandatory Baseline Dimensions

**Technical Identification:**

- Name: Banco Falabella Chile  
- Platform: Mobile Application (iOS and Android) and Multi-Channel Services (Official WhatsApp Business API)  
- Version Analyzed: Android Mobile App (Production Release)  
- Analysis Date: October 2026  
- Official Website: [https\://www\.bancofalabella.cl/](https://www.bancofalabella.cl/)

![][image9]

**Target user profile:** Retail banking clients, credit card holders (CMR), and everyday account owners requiring fast balance inquiries, monthly debt payments and immediate account security verification on mobile devices.

**Value Proposition:** A simplified, mobile-first banking environment that eliminates financial jargon, offers transparent debt breakdowns and facilitates one-tap billing payments alongside immediate conversational security notifications.

**Core Functionalities:**

1. Account Statement Breakdown: Visual overview of monthly credit and debt cycles, including prior balances, recent charges, and administrative fees.  
2. In-App Debt Payment Gateway: Segmented payment options (total billed amount, minimum payment, or custom amount) integrated into a single high-contrast flow.  
3. Multi-Channel Security & Device Verification: Real-time out-of-band alerts via official WhatsApp channels allowing instant confirmation or rejection of unrecognized logins.  
4. Transactional History & Digital Receipts: Immediate feedback on settled debts and downloadable accounting receipts.

**Onboarding Flow:** Native mobile onboarding leveraging biometric authentication (fingerprint/face recognition) or PIN passcodes, leading directly into account dashboards with prominent balances and contextual banners.

**Navigation Patterns:** Mobile tab bar paired with hierarchical card navigation. Complex multi-step actions are encapsulated in modal sheets and dedicated transactional views with explicit back and close triggers.  
Visual Design and Consistency: Clean mobile design system aligned with brand green accents. High visual contrast between background containers and actionable cards. Uses standardized semantic icons (downward/upward arrows, checks) and plain conversational microcopy to demystify financial figures.

**Observable Accessibility:**

- High color contrast ratios complying with WCAG mobile standards across major numeric figures and primary call-to-action buttons.  
- Touch targets comfortably exceed 48x48 dp across cards, lists, and bottom action buttons, supporting effortless one-handed thumb interaction.  
- Visual status indicators are paired with descriptive microcopy, ensuring accessibility for users with limited financial literacy.

## 3.3 Annotated Visual Evidence

**Screenshot 1:** Account Statement Summary and Expense Breakdown  
![][image10]

1. **Highlight:** Uses plain conversational helper text ("Te mostramos esto para que sepas...", "Esto es lo que pagaste...") under every accounting category, demystifying technical banking terminology for non-expert users (Heuristic: Match between system and the real world).  
2. **Highlight:** Employs semantic color coding and badges, highlighting returns and payments in green with checkmark icons ("-\$68.130") while keeping outgoing charges visually neutral (Heuristic: Consistency and standards / Recognition rather than recall).  
3. **Highlight:** Establishes strong visual hierarchy by emphasizing the total billed amount ("Monto facturado: \$106.040") alongside its explicit due date ("10 de octubre"), clearly distinguishing it from secondary obligations like the minimum payment (Heuristic: Visibility of system status).  
4. **Area for Improvement:** The disclaimer banner clarifying that the screen is only an informational summary sits at the very bottom of the viewport, requiring vertical scroll and risking lack of visibility for hurried users (Heuristic: Help and documentation).

**Screenshot 2:** Credit Card Payment Selection and Settlement  
![][image11]

5. **Highlight:** The top persistent card displays critical temporal context (due date "10/10/2026" and billing cycle) before payment, eliminating the need to navigate back to verify billing periods (Heuristic: Recognition rather than recall).  
6. **Highlight:** Payment options are laid out as large, high-affordance selectable cards ("Monto total facturado", "Monto mínimo", "Otro monto") with clear green boundary indicators, perfectly optimized for one-handed mobile thumb reach (Heuristic: Flexibility and efficiency of use / WCAG touch target standards).  
7. **Highlight:** Features a persistent, full-width primary action button ("Ir a pagar") pinned at the bottom, offering immediate affordance to complete the financial flow (Heuristic: Flexibility and efficiency of use).  
8. **Area for Improvement:** Displays zero-balance placeholders ("\$ 0") while maintaining the primary "Ir a pagar" CTA in an active green state, creating ambiguity around whether an empty submission will trigger an inline validation error (Heuristic: Error prevention).

**Screenshot 3:** Conversational Multi-Channel Security Alert  
![][image12]

9. **Highlight:** Employs an authenticated external channel (official WhatsApp Business with verified green/blue check) to notify sensitive security events, meeting users in a daily application they already trust and understand (Heuristic: Visibility of system status / Flexibility and efficiency of use).  
10. **Highlight:** Transparently itemizes session metadata—including exact timestamp, masked RUT, and client operating system ("Android")—allowing unequivocal identification of access context (Heuristic: Recognition rather than recall).  
11. **Highlight:** The message body explicitly explains the consequences of each choice in advance (“Presiona ‘No fui yo’ para desconocer el ingreso y tus claves y productos se bloquearan por seguridad”) preventing accidental critical lockouts and building user certainty (Heuristic: User control and freedom / Error prevention).  
12. **Highlight:** Replaces free-text typing with constrained one-tap quick-reply buttons (“Sí, fui yo” and “No fui yo”), eliminating ambiguity, streamlining binary decision-making and drastically reducing cognitive load and response time (Heuristic: Flexibility and efficiency of use / Error prevention).

[image1]: ./images/benchmark/SistemaAPR/1_SistemaAPR.png
[image2]: ./images/benchmark/SistemaAPR/2_SistemaAPR.png
[image3]: ./images/benchmark/SistemaAPR/3_SistemaAPR.png
[image4]: ./images/benchmark/SistemaAPR/4_SistemaAPR.png
[image5]: ./images/benchmark/ComunidadFeliz/1_ComunidadFeliz.png
[image6]: ./images/benchmark/ComunidadFeliz/2_ComunidadFeliz.png
[image7]: ./images/benchmark/ComunidadFeliz/3_ComunidadFeliz.png
[image8]: ./images/benchmark/ComunidadFeliz/4_ComunidadFeliz.png
[image9]: ./images/benchmark/BancoFalabella/1_FalabellaBank.jpg
[image10]: ./images/benchmark/BancoFalabella/2_BancoFalabella.png
[image11]: ./images/benchmark/BancoFalabella/3_BancoFalabella.png
[image12]: ./images/benchmark/BancoFalabella/4_BancoFalabella.jpg
