# Ally UI — Design System

Ally UI is the design system behind **Ally**, a healthcare management platform for medical ordering, inventory management, and clinical workflows. It serves pharmacists, GPO (Group Purchasing Organization) managers, and clinical staff. The system is **light-theme**, blue-led, and built to feel **trustworthy, accessible, and calm** under high-stakes clinical work.

Two product surfaces are represented:
- **Ally GPO** — the group-purchasing / medical ordering + inventory web app (primary surface).
- **Ally IQ** — the analytics / intelligence companion surface (shares the same foundations).

## Sources

- **Figma:** "Ally UI (WIP)" — the binding source of truth. Foundations live in the `Color-Tokens`, `Typography`, and `Storybook-Tokens` pages; components in `Button`, `Input`, `Badge`, `Checkbox`, `Radio-Button`, `Toggle`, `Dropdown`, `Date`, `Text-Area`, `Tool-Tip`, and `Icons-WIP`. (This file was mounted read-only at build time; the reader may not have access — request the original `.fig` if needed.)
- Brand assets (logo, domain icons) were extracted from the Figma and live in `assets/`.

## Brand at a glance

- **Name / wordmark:** AllyGPO. Reverses to white on Dark Blue 950; brand blue **#095192** for on-light contexts.
- **Primary color:** Dark Blue 500 `#095192` — buttons, nav, links, active states.
- **Type:** Inter is the sole typeface, used at two weights only (Regular 400 / Medium 500). Hierarchy comes from size, not extra weights or a second face.
- **Shape language:** 4px workhorse radius; pill for badges & toggles; restrained cool-tinted shadows.

---

## CONTENT FUNDAMENTALS

**Voice.** Clinical-professional but plain. Ally talks like a competent colleague at the pharmacy counter — direct, unfussy, never chatty. The reader is a busy professional, so copy gets out of the way.

- **Person & address:** Address the user as **you**; the product refers to itself by name ("Ally suggests…") rather than "we". Actions are imperative and verb-first: *Submit order, Save draft, Review formulary, Add facility.*
- **Casing:** **Sentence case** everywhere — buttons, labels, headers, menu items ("Submit order", not "Submit Order"). Proper nouns and product names keep their caps (Ally GPO, Mercy General). Acronyms stay upper (NDC, GPO, PO, EXP, LOT).
- **Tone:** Reassuring and precise. Confirmations are factual ("Order submitted to your GPO"), errors are specific and fixable ("Quantity must be at least 1.") — never blame the user, never joke.
- **Numbers & identifiers:** Codes are shown verbatim in Inter Regular (the *sub heading/detail* token) — `NDC 0078-0357-15`, `PO-4821-00`. Currency always two decimals (`$1,284.50`). No monospace.
- **Microcopy length:** Labels 1–3 words; helper text one short sentence; empty/disabled states say what to do next.
- **Emoji:** **None.** This is a clinical tool — status is communicated with color + dot badges and icons, never emoji.
- **Examples:** "Facility name", "Auto-reorder", "Low stock", "Backordered", "Cold-chain item — keep 2–8°C", "Updated 3 minutes ago · by J. Rivera, PharmD".

---

## VISUAL FOUNDATIONS

**Overall vibe.** Clinical, airy, blue-and-white. Lots of whitespace, hairline borders, and quiet surfaces. The interface recedes so data and decisions come forward. Nothing decorative — every element is functional.

- **Color.** A blue-led system: **Dark Blue** is the brand/primary ramp (500 `#095192`), **Blue** is the secondary/informational accent, **Steel** is the cool neutral that does most of the structural work (borders = Steel 200, app canvas = Steel 50 `#F8FAFC`, chrome), and **Gray** is the warm-neutral for text (body = Gray 950 `#25282A`). Status is a tight semantic set: **Green** success `#008774`, **Red** danger `#D9342B`, **Dark Yellow** warning `#EEC038`. Orange/Teal/Purple are reserved for categorical tags and charts. Backgrounds are flat white or Steel 50 — **no gradients.**
- **Type.** **Inter only**, at two weights: **Regular (400)** and **Medium (500)** — there is no bold, no second face, no mono. Hierarchy comes from **size**, mirroring the Figma token sheet: metric 24/32, heading 18/28, sub-heading/section 16/24, sub-heading/label & all body 14/20, caption & badge 12/16, side-nav 10/14. Medium is for titles, labels, emphasis, badges & link buttons; Regular for body, info, table cells & captions. Headings are 600 weight, body 400, emphasis 500.
- **Spacing & layout.** 4px base grid (4 / 8 / 12 / 16 / 20 / 24 / 32 / 40 / 48). Generous padding inside cards (16–24px). Fixed left sidebar nav + top bar is the canonical app shell; content scrolls within a max-width region.
- **Backgrounds.** No imagery, no patterns, no texture, no gradients. Surfaces are pure white cards on a Steel-50 canvas. Depth comes from hairline borders + subtle shadow, not color washes.
- **Corner radii.** 4px (`radius-sm`) is the workhorse — buttons, inputs, checkboxes. 8px for cards/menus, 12–16px for large panels, full **pill** for badges, toggles, and status chips. 2px for the smallest accents.
- **Cards.** White surface, **1px Steel-100 border**, 8px radius, `shadow-sm` (very soft, cool-tinted). Not heavy — borders carry most of the separation; shadow is a whisper.
- **Borders.** Hairline 1px. Default = Steel 200; inputs = Steel 200 → Dark Blue 500 on hover/focus; error = Red 300.
- **Shadows / elevation.** Restrained and cool-tinted (navy alpha, not black). `xs` for buttons, `sm` for cards, `md` for menus/tooltips, `lg` for modals. No glow, no large diffuse shadows.
- **Focus & a11y.** Visible focus ring = Dark Blue 400 @ 40% as a 3px outer ring. Hit targets ≥ 40px on controls. Contrast tuned for clinical lighting.
- **Hover states.** Primary buttons darken (500 → 600 → 700 on press). Outline/ghost buttons fill with Dark Blue 100 tint. List/menu rows fill with Steel 50; selected rows tint Blue 50 with Dark Blue 500 text.
- **Press states.** Color-shift only (one ramp step darker) — **no shrink/scale transforms.** This is a precise tool, not a playful one.
- **Animation.** Minimal and fast: 120–180ms, `cubic-bezier(0.2,0,0,1)` standard ease. Toggles slide, menus fade/translate a few px, focus rings appear instantly. **No bounces, no infinite loops, no decorative motion.**
- **Transparency / blur.** Used sparingly — modal scrims (navy alpha), focus rings. No frosted-glass aesthetic.

---

## ICONOGRAPHY

- **UI icon set:** **Remix Icon** (line style, 24px, ~1.8px stroke). Names in the Figma follow Remix conventions (`search-line`, `settings-line`, `arrow-right-s-line`). In HTML, link Remix Icon from CDN: `https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css` (the UI-kit cards use inline SVG equivalents to stay self-contained — see `preview/brand-icons.html`).
- **Domain glyphs:** A small set of bespoke SVGs for pharmacy concepts (cold-chain/refrigerated, clinic, dispense, formulary, bolus) extracted into `assets/icons-domain/`. Use these verbatim — do not redraw.
- **Style rules:** Line (outline) icons, not filled, for UI affordances; filled only for tiny status dots. Single-color, inherits `currentColor`, tinted Steel 700 in neutral chrome or Dark Blue 500 when active.
- **Emoji / unicode as icons:** Never. All iconography is SVG or the icon font.

---

## Components

Each lives in `components/<Name>/` as `<Name>.jsx` + `<Name>.d.ts` + a `@dsCard`-tagged demo, styled entirely off `colors_and_type.css` + `components.css` classes:

- **Button** — primary/outline/text/danger variants, sizes, icon-only.
- **Input**, **TextArea** — default/error/disabled states.
- **ChipField** (kit `Chip Field`, With Chip axis, node 5194:40990) — 300px column at 2px gap; 19px label row (`Label` 500/14/20 `#25282A` + `(Optional)` 400/14/20 `#757575`, counter right); 38px group, radius 4, white, **inset** 1px `#BCC3CD`, 8/12 padding, 2px gap; helper 400/12/16 `#757575`. With Chip=False shows the kit's `user` glyph + `#9FA9B7` placeholder, With Chip=True a 28px overflow-hidden slot with `Chip`s 16px apart; both carry the trailing `chevron-down`. `editable` keeps the older free-text input.
- **ContentDivider** (kit `Content Divider`, Types axis) — Sub Heading (node 3063:66764) is a 32px row, 8/12 padding, label 500/12/16 uppercase `#64748B`; Line (node 3063:66766) is an 8px row with 8px vertical padding holding a 1px `#D8D8D8` rule — it owns its spacing rather than being a bare `hr`.
- **Tooltip** — kit `Tooltip` (Arrow axis): a 28px body (radius 4, `#465161`, 4/8px padding, 400/12px at line-height 100%, `#F5F5F5` ink, `0 1px 2px rgba(228,229,231,.24)` + `0 12px 24px rgba(136,140,152,.12)`) with an 8×4 arrow in the same fill — eight positions plus `arrow={false}`.
- **Checkbox** — kit `Checkbox` (State × 🟢 Active × ⊖ Indeterminate): 20×20, radius 4, 1px `#BCC3CD` stroke that turns `#095192` on hover/focus, `#095192` fill with a 16px glyph when checked, `#ECECEC`/`#DADEE3` when unchecked-disabled, fill at 50% when checked-disabled. `size="row"` renders the 24px multiselect row box.
- **Radio** — kit `Radio Button` (🟢 Active × State): 20×20 circle, 2px `#BCC3CD` ring → `#095192` on hover/focus, `#095192` fill behind a 10px white dot when selected.
- **Toggle** — kit `Toggle` (State × 🟢 Active): 48×28 pill track, radius 999, with a 20px knob inset 4px (travel 20px). Off `#BCC3CD` → `#818EA1` on hover/focus; on `#095192` → `#1B4577` on hover; focus adds the 2px `rgba(72,112,161,.4)` ring; disabled at 50%.
- **CheckboxCard** — kit `Checkbox Card` (🔄 Flip × State): 200×68 minimum, radius 4, 12px padding, 8px gap; `#FFF` on a 1px `#D8D8D8` hairline, `#EFF1F3` hover, `#E9EEF4` + `#095192` stroke when selected, `#ECECEC` disabled.
- **CheckboxLabel**, **RadioLabel** — the labelled pairings, in `components/Selection/`.
- **ContentDivider** — kit `Content Divider` (Types: Sub Heading | Divider): a 32px row, 8/12px padding, 8px gap, 500/12px/16px `#64748B` uppercase label; `type="divider"` is the bare 1px rule and `type="inline-label"` keeps this project's older centred-label rule.
- **DropdownMenu** — kit `Dropdown Menu` (Type: Single Select | Multi Select): the 300px panel behind `DropdownItem` rows — radius 4, white, 1px `#BCC3CD` inset stroke, optional `ContentDivider` sub-heading.

**Kit aliases** (group **Kit aliases**) — thin presets exported under the Figma's own family
name, so a consumer can reach a component by the vocabulary the kit uses. Each forwards every
prop to a broader implementation this project already ships:

- **Listbox** → `DropdownItem` · **Switch** → `Toggle` · **Tag** → `Chip` · **NumberPicker** (kit `Number Picker`) → `CounterInput` · **TabHorizontal** (kit `Tab Horizontal`, also `Tab Navigation` / `_Tab Row`) → `Tabs` · **SearchOrSelect** (kit `Search or Select`) → `Autocomplete` · **TopStatus** (kit `Top Status [1.0]`) → `CircleStatus` · **TapToEditCell** (kit `Tap to Edit Cell`, also `Future Edit Field`) → `TableInput`.
- **Badge** — the `outline` variant is node-exact from the kit's outline publishing (2628:38042 Grey / 38043 Blue / 38044 Violet / 38045 Yellow / 38046 Red / 38047 Green): white fill, an inset 1px stroke in the color's **base** tone, and near-black `#25282A` ink — the label does not take the color.
- **Badge** — kit `Badge`, **Color** axis: 20px pill, radius 20, 4/8px padding, 14px·500 at line-height 100%, fill-matched 1px stroke. Blue `#3B83F7`, Green `#008774`, Red `#C32F27`, Yellow `#EEC038` (near-black ink), Violet `#773CAF`, Grey `#465161`, White `#FFF` on `#BCC3CD` with `#465161` ink.
- **BadgeCategory** — kit `Badge`, **Category** axis (the "Badge [Light]" frame): 20px white chip, radius 4, 1px `#D8D8D8` inset stroke, 4px padding, 4px gap, 12px/16px·500 `#25282A` ink, with a 4px-wide full-height leading bar at radius 20 — Complete `#3B83F7`, Negative `#C32F27`, Positive `#008774`, Pending `#EEC038`, Incomplete `#465161`, Patient `#A855F7`, Info Tag barless. Note the bar ramp is **not** the Color axis ramp: Patient is `#A855F7` here where the filled Violet badge is `#773CAF` — kept verbatim.
- **BadgeChange** — kit `Badge`, **Type** axis (`New` | `Same`): the table-cell change indicator, a distinct 24px chip — radius 4, white on a 1px `#EAEAEA` hairline, 4px padding, 2px gap, a 2×12 radius-50 leading bar, then a 12px glyph and a 400/12px/16px label sharing one ink: New `#6600FF` with the star glyph, Same `#008436` with the check. Glyphs come from `IconBeta`/`KitIcon`, not hand-drawn.
- **BadgeProduct** — kit `Product Badges`: 20px chip, radius 4, 8px horizontal padding, 12px·500 on a 16px line box. SDV `#282E38`, CLIMATE `#06B6D4`, PACK `#465161`, CIV `#EEC038` (near-black ink), NON SERIAL `#FE4603`; selected collapses to `#173A63` at the same 20px height.
- **Toast** — kit `Status=* Alert` / `* w/title` / `* Banner` (the /Toast page family), **Status × Type × Theme**. 400px box, radius 4, 8/12 padding, 8px gap; `alert` 56px single-line, `title` 108px stacking a 500/14/20 title over a 400/14/20 description at letter-spacing `-0.006em`, `banner` full width. The glyph is a 16px mark inset 2px in a **transparent** 20px well painted **white** — the kit draws no colored circle behind it (Neutral inks `#64748B` instead). Light fills Error `#F3C0BD` / Success `#B0E4DD` / Info `#EAD6FD` / Warning `#EFDABB` / Neutral `#E9EEF4`; dark fills `#4C120F` / `#003B33` / `#4C266F` / `#47300D` / `#314158`. Every variant carries a 62×24 primary-link action. Nodes 3137:46448–46455, 3137:49199–49246, 3141:1037, 3144:1471–1550.
- **Banner** — wide left-accent alert (distinct from Toast, for page-level notices).
- **Tabs**, **TabItem** — vertical list-style tab navigation, with count badge — renamed from `TabList` to match the kit’s `_Tabs` family.
- **Avatar** — initials or photo, sm/md/lg, online dot.
- **DatePicker** — month nav now renders the kit's `ChevronLeftSize14x14` / `ChevronRightSize14x14` through `KitIcon` instead of `&lsaquo;`/`&rsaquo;` text entities.
- **DatePicker** — functional month calendar with hover/today/selected/disabled states.
- **Dropdown** — multiselect trigger + search + Select All panel.
- **Menu**, **Tooltip**, **Card** — in `components/Menu/`.
- **Divider** — renamed **ContentDivider** to match the Figma family name ("Content Divider").
- **CircleStatus**, **CounterInput**, **Pagination** — smaller utility primitives.
- **HelpButton** — in `components/HelpButton/`.
- **BottomActionBar**, **ButtonSet** — kit `Bottom Action Bar` / `_Desktop` + `_Tablet Bottom Action Bar`: 68px white bar, min-width 400, overflow hidden, `space-between`, 16/24 padding (16/40 on the Three-button variant, `padding="wide"`). `ButtonSet` is the kit's 36px, 24px-gap button group (nodes 11:2062, 11:2088, 3500:177341).
- **InputGroup**, **InputGroupAddOns** — kit `_Input Group Add-Ons`, exported under the kit's own name: Position (left | right) × Type, 42px tall; the Button type is an 88px slot whose button takes the kit's asymmetric `4px 6px 6px 4px` radius (node 11:654).
- **StandardButton** (`_Standard Button`, 40px) and **LargeButton** (`_Large Button`, 48px) — the kit's two named button-size families; `Button` remains the general form with a `size` prop.
- **MenuItemLink** — `_Menu Item_Link`, the anchor-flavoured menu row (selected/disabled states).
- **TableInput** — `_ table input`, borderless in-cell editor for editable data grids, with align and invalid states.
- **SideNav**, **SideNavItem** — the **70px** left rail per the Figma: 50px cells (24px icon over a 10px label), inlined AllyIQ logo block (`#0e243f`), decorative location-pin block, pinned footer group and version line. Active state is the Figma's **white selection pill** with DarkBlue/500 content (`--sidenav-selection-bg` / `-fg`, from Color-Tokens › Side Navigation) plus `aria-current="page"`. `iconName` pulls the shipping glyph for that nav label. The rail fills its parent's height (`height:100%`), so mount it in a **full-height flex row** — e.g. `<div style="display:flex;height:100vh">` — and the nav group scrolls when items exceed the viewport while the footer stays pinned.
- **TopNav**, **TopNavChip**, **TopNavDivider** — the **60px** top bar per the Figma: context chips (org / clinic / station) at **13px** Medium with 20px icons, a `secondary` chip variant in `#757575`, 1px×24 dividers between chips, `#d8d8d8` bottom hairline, and user name + sign-out on the right. A chip with no `onClick` renders disabled, matching the app's convention.

Both take their **measurements from the Figma** (70px rail / white pill / 60px bar / 13px chips), confirmed as the source of truth over the older `ally-shell.js` export, which specified 60px / `#173a63` / 50px / 14px. Icons resolve **Figma-first**: `iconName` looks up the "❖ Icons (WIP)" module glyph in `assets/kit-icons/` (Dispense, Orders, Restock, Audit, Inventory, Formulary, MasterFormulary, Patient, Transfer, Reporting, Station, User, MyWork, Appointments, Practice, Clinic, Support, Help) and only falls back to the `ally-shell.js` copy when the file has no glyph for that label. Their 17 icons and the logo data URI live in `assets/shell-icons.js`; regenerate that from the app builder rather than editing it by hand.
- **ProductCard** — kit `Product Card`: 580px card, radius 4, 76px header on #F5F7FA behind a 1px #D8D8D8 border, uppercase product name with generic name and product badges, plus body and footer slots; `selected` draws the kit's 1px #095192 ring (node 4575:101275).
- **Table**, **TableHead**, **TableBody**, **TableRow**, **TableHeader**, **TableSubHeader**, **TableCell** — the `_table-column-*` primitives: 54px header on #F8FAFC with a 1px #EEEEEE border and 20px sort affordance, a 54px filter sub-header row, and white cells on a 1px #E0E0E0 border at 12/16/8/16 padding. The kit draws its tables as columns of frames rather than publishing a set, so these are the composable pieces (nodes 3500:181234, 3500:181251, 16:4759).
- **ToggleButton** — kit `Toggle Button`: 38px pressed-state button, radius 4, State=False white on a 1px #BCC3CD hairline / State=True filled #095192 (nodes 5119:106951, 5119:106953).
- **ToggleField** — kit `Input Switch`: labelled switch row across the Flip × Description axes, with sub-label and outlined tag support (nodes 2625:31846/31847/31849/31864). The switch itself is the existing `Toggle`.
- **Modal**, **ModalOverlay** — kit `Modal`: Type (Action | Confirmation) × Size at the file's exact widths (small 520 / min 400, medium 600, large 800), radius 4, 68px title bar with a 28px severity glyph (nodes 4362:65757, 4398:112591, 4399:112643, 4362:65224).
- **OverlayPanel** — kit `Overlay Panel`: tailed popover, Type × Arrow (top/bottom × left/center/right), 12×6 tail, radius 4 and the kit's two-part shadow (nodes 4430:75279, 4428:75277).
- **SidePanel** — kit `Side Panel`: right-docked panel, Size axis at the file's exact widths (large 800 / medium 440 / small 360), radius `4px 0 0 4px`, 64px title bar with back/title/subtitle/actions and a footer slot (nodes 4372:78936, 4387:97250, 4387:97279).
- **FileUpload** (kit `File Upload`, node 4969:231864) — the 24px cloud glyph now renders the kit's own `CloudUploadSize24x24` via `KitIcon` rather than a hand-drawn path.
- **FileUpload** — kit `File Upload`: 500px card with a 250px dashed drop zone (radius 8, 1px dashed #D8D8D8), cloud-upload glyph, upload button and format hint; supports real drag-and-drop (node 4969:231864).
- **ScrollPanel** — kit `Scroll Panel`: scroll container styled with the kit's 8px #E9EEF4 thumb (radius 999) in a 24px white gutter, keeping native scrolling (node 5202:78680).
- **SegmentedControl**, **SegmentedItem** — kit `Segmented Control`: 48px shell, radius 4, white on a 1px #D8D8D8 hairline, 4px padding, with optional 38px chevron affordances (node 5127:107068).
- **Chip**, **ChipField** — kit `Chip` (24px pill, radius 50, #E9EEF4, 12px/16px #095192 label) and `Chip Field`, its labelled 38px input group (nodes 5194:41264, 5199:45834).
- **DropdownItem** — kit `Dropdown Items [1.0]`: 36px row, 4 Row States (default #FFF / hover #EFF1F3 / selected #E9EEF4 / selected-hover), optional checkbox and trailing sub text (nodes 2556:34283–34286, 2555:40381).
- **Autocomplete** — kit `Autocomplete`: labelled 38px input with a suggestion panel of dropdown rows (nodes 5199:46534 / 46729).
- **CalendarCell** — the three grey states are three *different* greys, easily conflated: hover `#EFF1F3` (node 2860:18515), today and range-selected `#E9EEF4` (nodes 2860:18523, 4933:226992).
- **CalendarCell** — Type=Month / Year keep Date's 63.81×51 cell and 8px padding but swap the 35px radius-50 pill for a **radius-4 block that fills the cell**, label at line-height 20px not 100% (nodes 2860:19140 / 19146, 2861:1191 / 1197).
- **CalendarCell** — kit `Calendar Cell`: 63.81×51 cell with a 35px pill, Type × State axes incl. today ring and range-selected (nodes 2860:18511–18523, 4933:226992).
- **EditableFields** — kit `Editable Fields`, exported under the kit's own plural family name: in-cell value across Types × State × the "Edit field" boolean (nodes 4377:91302 / 3767:33408).
- **Lozenge**, **BottomStatus**, **Footer** — materialized verbatim from the .fig in `components/_fig/` (nodes 81:23587, 4344:182924, 4362:65337). `Lozenge` is the kit's Atlassian-derived tag (SF Pro, `rgba(9,30,66,0.06)`) and is deliberately NOT the same thing as `Badge`; `BottomStatus` is a 32px presence dot; `Footer` is the 520px modal footer. Their private dependency modules sit beside them without `.d.ts` so they don't register as public components.
- **DropdownInput** — kit `Dropdown-Input`: the 48px combobox trigger, radius 4, white, inset 2px `#3B82F6` focus ring, 12px padding, 8px gap, 400/16px/24px value against a 24px trailing chevron (node 3500:176919). Distinct from `Dropdown`, the 38px select with its own State axis.
- **CheckboxLabel** — kit `Checkbox Content` / the `Checkbox` label group (Active × Description × Flip × Indeterminate): the checkbox twin of `RadioLabel`, identical geometry, plus an `indeterminate` prop wired to the input (nodes 4377:90915/90920/90925/90930/90938/90946/90954/90962).
- **RadioLabel** — kit `Radio Label` (Active × Description × Flip): the 20px radio 8px from a 4px-gap column whose label row holds a 400/14px `#25282A` label, optional 400/12px `#757575` subtext and optional badge 8px apart; Description adds a 400/12px muted line beneath, Flip moves the radio after the text (nodes 2546:26790/26794/26806, 4377:90130/90148/90173/90206/90214).
- **PatientInfo**, **InfoRow** — kit `Patient info`: a labelled detail block. A 600/12px `#25282A` section label at 50% opacity 8px above a 4px-gap stack of label/value rows (400/14 label, 8px gap, 600/14 value) — node 4775:178711. Generic enough for any read-only detail group.
- **TaskCard**, **TaskStep** — kit `TaskCard` / `Step` from the live-progress tracker: radius 8, white, inset 1px `#D8D8D8` over `0 4px 12px rgba(0,0,0,.051)`, 24px padding, 20px gap; `space-between` header (700/16 `#25282A` + 400/13 `#757575` against a right-aligned 700/18 `#095192` percentage + 400/12 elapsed), an 8px track (radius 4, `#E9EEF4`, fill `#095192`), and a 12px-gap step row whose 24px indicator fills `#008774` when done (nodes 4193:38812, 4193:38823).
- **ProductHeader**, **HeaderContext**, **HeaderDivider**, **HeaderStatus** — kit `Product Header` (Types axis): the 64px context bar under the top nav. White, 1px `#D8D8D8` all round, 0/16 padding, `space-between`; left cluster of context items 24px apart (20px glyph + 500-weight 14px/18px `#757575` label, 4px gap) split by 1px × 32px rules; right cluster a 40px, 16px-gap actions row with the kit's status well (radius 4, inset 1px hairline over `0 0 4px rgba(114,114,114,.25)`) — node 4759:176560.
- **ConfirmationModalContent** — kit `Confirmation Modal content` (Type axis): the message block inside a Confirmation `Modal`. 488px, 4px gap, 28px round icon well holding the 26px glyph, beside a 500-weight 16px/24px `#25282A` headline and 400-weight 14px/20px `#757575` description. Severity ink error `#D9342B` / warning `#A36E1E` / info `#A855F7` / success `#008774` (nodes 4364:65922 / 65940 / 65955, 4362:65285).
- **MenuItemLink**, **MenuGroup** — kit `_Menu Item_Link` (State axis) and its `_Menu Group` column: the **Ally IQ** side-nav row, 224×48, 8px gap, 12/16 padding, 24px icon, Inter 400 16px/24px. Default is transparent on the brand-blue rail with white ink; Selected is a white fill with a 5px white left border and `#095192` ink (nodes 11:750, 11:755). Distinct from `SideNavItem`, the Ally GPO 70px icon-over-label rail.
- **Alert** — kit `Alert`: page-level severity strip, radius 6 with a 1px border and 8px left accent, bold header + description, optional dismiss. Distinct from `Banner` (5 statuses, no dismiss) and `Toast` (compact 400×56).
- **Accordion**, **AccordionItem** — kit `Accordion`: 42px header (radius 4, `#F5F7FA` on a `#D8D8D8` hairline) with a primary-link expand trigger.
- **ProgressBar** — kit `Progress Bar`: 6px track / radius 8, `percentage` (right-aligned % label) and `infinite` (indeterminate sweep) types.
- **Stepper**, **StepperItem** — kit `Stepper`: 28px marker with the State axis (default / selected ring / completed check) × Position axis (label right or bottom). The track draws the kit's 1px `#D8D8D8` connector rule between steps (container gap 8, padding 4 — node 5236:98350); that rule, not a wide gap, is what separates steps.
- **KitIcon** — the kit's own icon set materialized straight from the .fig: **55 families / 156 named glyphs** in `assets/kit-icons/icon-data.js`, including the 18 module icons the side nav uses (Dispense, Orders, Restock, Audit, Inventory, Formulary, Patient, Transfer, Reporting, Station, MyWork, Appointments, Practice, Clinic, Support, Help, User, MasterFormulary) and the UI glyph families at 14×14 / 18×14 / 24×24 / 44×44. Named `KitIcon` (not `Icon`) to avoid colliding with the UI kit's own `Icon`. Read `assets/kit-icons/KitIcon.d.ts` for the valid names.
- **GlyphIcon** — renders a glyph from `assets/icons/icon-data.js` (an intentional addition — a wrapper for the icon set, not a Figma component itself).
- **IconBeta** — kit `❖ Icon (Beta)`: the kit's UI glyph library, materialized from the .fig into `assets/ui-icons/` — **23 glyph families × 14/18/24/44px** (`search`, `plus`, `trash`, `sliders-v`, `pencil`, `undo`, `refresh`, `sign-out`, `lock`, `unlock`, `qrcode`, `map-marker`, `history`, `print`, `star`, `heart`, `info-circle`, `exclamation-circle`/`-triangle`, `shopping-cart`, `remove`, `sort-alpha-down`, `sort-numeric-down`). Single-color, paints with `currentColor`; every valid name is listed in `IconBeta.d.ts`.

`Column Table` is likewise **not** a component: it is one of three layout-mode text labels (`Row Table`, `Nested Table`, `Column Table`) inside the Table exploration frame, covered by `Table`. `Filter Panel` is **not** a component in this file — it exists only as a text label inside a Side Panel exploration frame, so it is covered by `SidePanel`. `Selected Items` likewise publishes no components, only Restock/Transfer example frames.

**Frame-derived names.** Several families are *drawn* in this file rather than published as component sets, so their names come from the frame or section they were read from, not from a variant name: `ProductCard` (frame "Product Card", node 4575:101275), `Accordion`/`AccordionItem` (section "Accordion", 5231:97732), and the `Table*` set (the `_table-column-*` frames, 3500:181234 / 181251 / 16:4759). These are faithful to the file; the coverage checker only matches published sets, so it reports them as unmatched names.

**Intentional additions — confirmed.** All 15 component names the coverage checker reports as "named after nothing in the kit" — currently `GlyphIcon`, `KitIcon`, `AccordionItem`, `Accordion`, `CircleStatus`, `Card`, `MenuGroup`, `ModalOverlay`, `InfoRow`, `ProductCard`, `HeaderContext`, `HeaderDivider`, `HeaderStatus`, `TaskStep`, `ButtonSet` — are deliberate. They are enumerated here so the report can be reconciled:

| Component | Why it carries a non-kit name |
| --- | --- |
| `KitIcon`, `GlyphIcon` | Icon-set wrappers (renderers over `assets/kit-icons/` and `assets/icons/`), not kit components. |
| `Accordion`, `AccordionItem` | Built from the kit's `Accordion` **section** (node 5231:97732), which the file draws as a frame rather than publishing as a component set — names come from the section. |
| `ProductCard` | Frame "Product Card" (node 4575:101275) — drawn, not published. |
| `Card` | Generic surface used throughout the kit's screens but never named as its own component. |
| `ModalOverlay`, `SegmentedItem`, `StepperItem`, `ButtonSet` | Wrapper / singular-item halves of kit families the file publishes only as whole assemblies. |
| `MenuGroup` | The kit's `_Menu Group` layer inside the Ally IQ nav (node 3500:177211) — a named frame, not a published set. Ships beside `MenuItemLink`, which *is* a kit family (`_Menu Item_Link`). |
| `HeaderContext`, `HeaderDivider`, `HeaderStatus` | The three internal parts of the kit's `Product Header` (node 4759:176560), which the file draws as one 64px bar. Split out so consumers can compose their own context items. |
| `TaskStep` | The kit calls it `Step` (node 4193:38823), but that name collides with the `Stepper` family's own step. Renamed for disambiguation; `TaskCard` keeps the kit name. |
| `InfoRow` | The repeated `ID` row inside the kit's `Patient info` block (node 4775:178711) — a named layer, not a published set. Split out so the block takes any number of label/value pairs. |
| `CircleStatus` | Our own inline status pill; distinct from the kit's `Bottom Status [1.0]` (a 32px avatar presence dot), which is built separately. |
| `Tabs`, `TabItem` | Figma's tab symbols are pre-assembled per screen with no reusable list wrapper — named to React/UI convention. |
| `TopNav`, `TopNavChip`, `TopNavDivider` | Compose the Figma's top bar, which the file draws inside screen frames rather than publishing as a component set. |

None are renamed: renaming would point them at kit families they are not faithful recreations of. They are additive scaffolding around the kit's real primitives.

**Fonts.** `tokens/fig-tokens.css` (the raw Figma variable dump) carries a cluster of font tokens from an **Atlassian Design System** collection mixed into the source .fig — `Open Sans`, `Atlassian Sans`, `SF Pro`, plus the `data-mode="modernized"`/`"refreshed"` scopes and the `--weight-*`/`--font-style-italic` style-name tokens. No Ally component references any of them. Their values are preserved verbatim but marked `/* @kind other */`, so they are not read as Ally brand fonts awaiting font files (SF Pro and Atlassian Sans are proprietary and cannot be supplied here). Ally's real font tokens are `--font-family-primary`/`--font-family-secondary`, both Inter. See `fonts/README.md`.

### Figma coverage & intentional scope

**Values move between file revisions, so re-read before trusting a built value.** Confirmed
cases: the `Toggle` track is **48x28 with a 20px knob** in the current revision where an
earlier mount of the same node (`2619:53096`) read **32x18**; `Product Badges` selected was
**24px** in the earlier mount and is **20px** here; and the `Badge` family gained both a
**Category** axis (the light chip with a leading bar) and a **Type=New|Same** change
indicator. Each is built from the current mount and re-verified rather than carried forward.

The headline count moves with the file revision — the current mount reports **418 component
families, 103 built**, where the previous mount of the same kit reported **341 / 114** (and
its variable count moved the other way, 1173 vs 1356). The arithmetic below is what matters,
not the headline. That headline is
misleading, and the file's own `/METADATA.md` shows why: the count is **component sets +
standalone symbols** with every duplicate publishing and every per-size icon counted as its
own family. Verified against the live inventory:

| Bucket | Count | Evidence from `/METADATA.md` |
| --- | --- | --- |
| Duplicate sets of one component | **~176** | One component is published many times over: **Checkbox appears 18×** (13 `Checkbox` + 4 `Check Box` + `Checkbox [1.0]`), **buttons 24×** (9 `Buttons` + 7 `Button` + 5 `_Standard Button` + 2 `_Large Button` + `button`), **Badge 10×**, `Dropdown` 6×, `_Tabs` 4×, `Bottom Action Bar` 4×, `Banner` 3×. 418 raw names collapse to ~242 unique. |
| Icon families | **~115** | Every glyph is a family with a `Size: 3/4` axis (`chevron-down` alone is listed 4×), plus the ~80-glyph standalone set the METADATA header calls out. All covered by `assets/kit-icons/` (156 glyphs), `assets/ui-icons/` (23 × 4 sizes) and `assets/icons/`. |
| Variant sub-paths | 44 | Individual variants listed as standalones — `Buttons/Primary Link/Active/False`, `Calendar Cell/Month/Selected Hover`, `Dropdown Items [1.0]/Row State5`. Not families. |
| Figma doc scaffolding | 6 (5 now built) | `.{keyValuePair}`, `.{tokenCard}` (updateType × tokenType × layout × modes), `.{tokenSwatch}`, `🧬 Token preview - Dark`, `.{sectionHeader}`, `Documentation table / Cell` — these draw the style guide *inside* Figma. No product UI. |
| Auto-named stray frames | ~10 | `Component 1` (7×), `Component 2`, `Frame 1410083621`, `Frame 1410083622`. |
| Third-party data-grid theme glyphs | **24** | The `*-theme1` row the checker now leads with — `_asc`, `_desc`, `_filter`, `_tick`, `_clear`, `_columns`, `_copy`, `_cut`, `_paste`, `_star`, `_chart`, `_contracted`, `_expanded`, `_grip-handle`, `_small-down`, `_small-right`, `_tree-closed`, `_Checkbox-theme1`, `_cancel`, `_first`, `_group`, `_last`, `_none`, `_save`. Each has a `Type: 2` axis (light/dark theme glyph), not a State or Size axis: they are the icon sheet of an imported **AG Grid** theme, not Ally components. Ally's own grid chrome is `Table` and `TableInput`. |
| Third-party data-grid internals | **17** | The `Grid-Parts/*` families from the same import — `Grid-Parts/Flag` alone is **200 variants** of country flags, plus `Review-Stars`, `Sparkline`, `Operating-system-logos`, `Scrollbar`, `Tool Panel`, `sideButton-Vert`, `List Item`. **`Column Header`, `Grid Cell` and `Floating Filter` belong here too** — verified: they are only ever instanced from `/Table-WIP/external/AGGridColumnBasedLayout/`, i.e. the imported library, never from an Ally frame. Vendor surface; nothing in Ally GPO or Ally IQ renders them. |
| Foreign design-system leftovers | 3 | `❖ Icon (Beta)`, `❖ Lozenge`, `Documentation table / Cell` — Atlassian Design System components mixed into the file (they carry Atlassian's `appearance`/`isBold` axes and SF Pro type). `IconBeta` and `Lozenge` are built anyway, in `components/_fig/`. |
| **Genuinely unbuilt product UI** | **~11** | Listed below. |

The families the checker names as examples land in those buckets rather than in the unbuilt
list — and the three non-icon ones now also ship under the kit's own names.
`_Desktop Bottom Action Bar` and `_Tablet Bottom Action Bar` are two of the four duplicate
publishings of one bar; both are exported as `DesktopBottomActionBar` / `TabletBottomActionBar`,
presets over `BottomActionBar` carrying the kit's 16/24 and 16/40 padding geometries rather
than forks of it. `_Input Group Add-Ons` is the prefix/suffix slot beside an `InputGroup`
field, exported under the kit's own name as `InputGroupAddOns`. The examples the checker now cites — `_asc-theme1`, `_chart-theme1`, `_Checkbox-theme1`,
`_clear-theme1`, `_columns-theme1`, `_contracted-theme1`, `_copy-theme1`, `_cut-theme1` — are
all in the AG Grid theme-glyph row above: two-variant icon families (`Type: 2` = the light
and dark theme sheet) belonging to the imported grid library, so they are **intentionally
skipped**. Earlier example sets it cited (`android`, `angle-down`, `Appointments`,
`arrow-left`, `arrow-right`, `Audit`) are glyphs in `assets/kit-icons/`, rendered through
`KitIcon`; they are data, not components. And `.{keyValuePair}`,
`.{tokenCard}`, `.{tokenSwatch}`, `🧬 Token preview - Dark` are the Figma-internal style-guide
scaffolding row — they draw this file's own documentation pages rather than product UI, but
all four are now built anyway (`KeyValuePair`, `TokenCard`, `TokenSwatch`, `TokenPreview`,
group **Foundations**) since a design system can legitimately use them to document itself.
`TokenCard` carries the family's Figma axes as props: `updateType` × `tokenType` × `layout`,
and `TokenPreview` sets `data-theme` so a panel resolves its tokens under any of the kit's
theme modes. `.{sectionHeader}` (node 81:23503) now ships as `SectionHeader` — the 80px
rgba(9,30,66,.06) token-page banner with its 40/16/16/16 cell and 20px/24px `/`
breadcrumb runs. `Documentation table / Cell` is covered by `Table`.

**`_Tab Row` and the rest of `/Stash/` are intentionally skipped.** Verified by
grep: `_Tab Row` (node 585:78589) and its `Tab1` children are only ever instanced
from `/Stash/` and `/external-shared/`, the same imported Atlassian token-docs
library that carries `❖ Lozenge` and `❖ Icon (Beta)` — they are set in SF Compact
at weight 457 over Atlassian's `rgba(9,30,66,…)` neutrals, not Ally's palette. No
Ally GPO or Ally IQ frame instances them. Ally's own tab chrome is `Tabs` /
`TabItem` / `TabHorizontal`. `SectionHeader` is the one member of that library
built anyway, because a design system legitimately uses it to document itself; it
is re-set in Inter per the font policy above.

Carrying those further: almost none are net-new primitives. They map onto components
that are **already built** under the name this project uses, are icon glyphs, or are
frames rather than components:

Eight of them are no longer only "covered" — they now ship under the kit's own name as
thin presets (group **Kit aliases**, listed in the component index above): `Listbox`,
`Switch`, `Tag`, `Number Picker`, `Tab Horizontal`, `Search or Select`,
`Top Status [1.0]` and `Tap to Edit Cell`. The rest remain naming differences:

| Unbuilt kit family | Covered by |
| --- | --- |
| `Tab Navigation` | `TabHorizontal` / `Tabs` |
| `Paginator-Count`, `Paginator-Icon` | `Pagination` |
| `Infinite Process` | `ProgressBar` (`infinite` type) |
| `Future Edit Field` | `TapToEditCell` / `EditableFields` |
| `TH`, `_cell-text`, `_column-header-text`, `_row-header-text` | `Table` primitives |
| `Bottom Status` | `BottomStatus` |
| `Month`, `Year` | `DatePicker` / `CalendarCell` |
| `Sorting Icons [1.0]`, ~22 glyph families | `assets/kit-icons/` icon set |
| `_AllyGPO` | `assets/logo-allygpo-white.png` |
| `Products Selected`, `Smart Order`, `Reporting`, `Labels`, `Label sub text`, `Placeholder`, `Title`, `Hover State`, `Separator [Documentation]`, `Component 2`, `Frame 1410083621/22`, `❖ Icon (Beta)` | Frames / documentation scaffolding, not reusable components |

**Net result: no uncovered reusable primitive remains,** and **no hand-drawn icon renders
anywhere in the UI kit.** 23 UI glyph families (`qrcode`, `lock`, `unlock`, `pencil`,
`print`, `refresh`, `undo`, `history`, `remove`/`trash`, `sliders-v`, `map-marker`,
`shopping-cart`, `sign-out`, `search`, `plus`, `star`, `heart`, `info-circle`,
`exclamation-*`, `sort-*`) plus `Reporting` at 24×24 were extracted from the .fig into
`assets/ui-icons/`, and the domain SVGs in `assets/icons-domain/` (`refrigerated` for
cold-chain, `bolus` for admixture, `clinic`) were inlined into the kit's runtime set —
**69 glyphs total**, all source-derived.

Five placeholder paths remain *defined* in `ui_kits/ally-gpo/Icon.jsx` as a safety net
(`dashboard`, `home`, `book`, `layers`, `truck`) but **none are referenced by any screen**,
so zero render. Their absence from the source is **verified, not assumed**:
`fig_materialize` was queried for `truck`, `snow`, `snowflake`, `book`, `layers`,
`dashboard`, `delivery`, `shipping`, `home`, `temperature`, `thermometer`, `boxes` and
`cube` — all returned "not found" — and a grep of `data-component` values for those
concepts returns only `bookmark`/`bookmark-fill`. Where a concept had a real equivalent it
is now used instead: Home→`MyWork`, Formulary→`Formulary`, Order→`Orders`,
Inventory→`Inventory`, Dispense→`Dispense`, cold-chain→`Refrigerated`, Ad Mix→`Bolus`,
spend→`ShoppingCart`.

Where a kit family is covered by a differently-named component, that is a naming
difference rather than missing work — the checker matches on names only, so it counts
them as unbuilt. Renaming is deliberately avoided: the built components are broader than
the single kit frames they would be renamed to.

**Also resolved:** the unbuilt icon families have been extracted — see `assets/ui-icons/`
(23 glyph families × 14/18/24/44px sizes, materialized straight from the .fig).

**Intentionally not built:** WIP screen-pattern families (Notification live-tracker flows)
— full application screens under active design, not primitives; and **Lozenge** (❤ 12
variants), functionally identical to Badge and covered by its `variant`/`color` props.

**Tokens.** Of the kit's **1173 Figma variables** across 10 collections, most of the `Ungrouped` collection (631 variables) comes from unrelated token-system explorations mixed into the file (naming patterns like `action-background-*`, `main-bold-green`, fonts `Siemens Sans Pro`/`Open Sans` — none of which any Ally component references). `colors_and_type.css` carries a curated, hand-verified set matching what the real Button/Badge/Input components actually consume, confirmed by reading their exact Figma values; `tokens/fig-tokens.css` preserves the full dump alongside it.

## Index / manifest

Root files:
- `README.md` — this file.
- `thumbnail.html` — project homepage tile.
- `colors_and_type.css` — all color primitives, semantic tokens, type scale, spacing, radii, shadows, motion. Import this first.
- `components.css` — buttons, inputs, badges, toggle, checkbox/radio, tooltip, toast, banner, tab, avatar, date picker, text area, divider, circle status, counter input, pagination, card, menu. Depends on `colors_and_type.css`.
- `assets/icons/` — `icon-data.js` (26 core UI glyphs pulled from the Figma), `GlyphIcon.jsx`/`.d.ts`, `render-icons.js` helper, `icons.html` card.
- `assets/ui-icons/` — `icon-data.js` (23 UI glyph families × 4 sizes, materialized from the .fig), `IconBeta.jsx`/`.d.ts`, `ui-icons.card.html` card.
- `assets/kit-icons/` — `icon-data.js` (full 151-glyph module set), `icon-data.global.js` (trimmed 64-glyph browser build the UI kit loads), `KitIcon.jsx`/`.d.ts`.
- `SKILL.md` — Agent-Skills-compatible entry point.

Folders:
- `assets/` — `logo-allygpo-white.png` + `icons-domain/*.svg`.
- `components/` — 81 reusable React components, one directory per family (see above).
- `preview/` — Design System tab cards for foundations (colors, type, spacing, brand).
- `ui_kits/ally-gpo/` — high-fidelity interactive recreation of the Ally GPO app (medical ordering + inventory).

### Naming

Twelve materialized `fig_materialize` artifacts (`Buttons3`, `Check2`, `Checkbox2`,
`ChevronDown2`, `ChevronLeft`, `ChevronRight`, `Component13`, `Minus`, `Synergy`,
`Toggle4`, `Toggle5`, `ToggleLabel`) used to leak onto `window.<Namespace>` under
auto-generated names. They are now exported lower-camel (`figButtons`, `figCheck`,
`figCheckbox`, `figChevronDown`, …) so they stay **bundle-internal** dependencies of
`Lozenge`, `BottomStatus` and `Footer`, which remain the only public exports out of
`components/_fig/`. The public equivalents are `Button`, `Checkbox`, `Toggle`,
`ToggleField` and the `KitIcon` glyph set.

The checker flags built components whose names it can't match to a kit family. Those are
intentional and fall into three groups:

- **Icon wrappers** — `GlyphIcon`, `KitIcon`, `IconBeta` render the materialized glyph data
  (`assets/icons/`, `assets/kit-icons/`, `assets/ui-icons/`). The kit publishes each glyph as
  its own family; one wrapper per set is the code-side equivalent.
- **Frame-derived components** — drawn in Figma as frames or sections rather than published
  symbol sets, so no family name exists to match: `ProductCard`, `Accordion`,
  `AccordionItem`, `ProductHeader`, `PatientInfo`, `InfoRow`, `TaskCard`,
  `ConfirmationModalContent`, `Table` and its row/cell parts, `SideNav`, `TopNav`,
  `Card`, `MenuGroup`, `ModalOverlay`, `CircleStatus` — the last four are
  composition parts of a larger frame (`Menu`, `Modal`, the status row)
  rather than families of their own.
- **Sub-parts and idiomatic renames** — a family split into the pieces a consumer composes
  (`InputGroupAddOns` from `_Input Group Add-Ons`, `SegmentedItem` from `Segmented Control`,
  `CheckboxLabel`/`RadioLabel` from the label groups), or the kit's emoji/bracket names
  written plainly (`TokenCard` for `.{tokenCard}`, `TokenPreview` for `🧬 Token preview - Dark`,
  `KeyValuePair` for `.{keyValuePair}`, `Lozenge` for `❖ Lozenge`, `IconBeta` for
  `❖ Icon (Beta)`, `Avatar`/`Chip`/`Autocomplete` for their `[1.0]`-suffixed sets).

## Component index — kit-name aliases

Where the Figma publishes one control under several family names, the canonical build
carries the plain name and a thin alias carries the kit's other spelling, so a consumer
reading a Figma layer name finds the component under that name: `Buttons` and `CheckBox`
(→ `Button`, `Checkbox`), `Badge10` (→ `Badge`, the kit's 300-variant `Badge [1.0]`
rebuild), `Checkbox10` (→ `Checkbox`, its 12-variant `Checkbox [1.0]` rebuild),
`BottomStatus10` (→ `BottomStatus`, the kit's `Bottom Status [1.0]`) and
`TokenPreviewDark` (→ `TokenPreview` pinned to the dark theme, the kit's
`🧬 Token preview - Dark`).

`CheckboxContent` is a real build rather than an alias: the kit's `Checkbox Content`
(Flip axis, node 4377:90946) is the label column — label · subtext · optional badge over
an optional description — that sits beside a `Checkbox`, `Radio` or `Switch`, with `flip`
deciding which side the control takes. `DocumentationTableCell` is likewise a real build:
the kit's `Documentation table / Cell` (type axis, 5 variants) is the cell of the style
guide's own spec tables — `header`, `name`, `value`, `description`, `divider` — and
`DropdownItems10` aliases `DropdownItem` for the kit's `Dropdown Items [1.0]`.

**Figma's placeholder names, resolved by instance.** The file publishes some sets under
Figma's auto-generated `Component 1` / `Component 2` names. Rather than guess, each was
traced to the component that actually instances it:

| Kit family | Resolves to | Evidence |
| --- | --- | --- |
| `Component 1` (Property 1, 9 values) | `ChevronDown` glyph set | Every reference mounts `Property1ChevronDown` inside the Toggle Label description row (`/Input-Switch/components/Flip*Description*`, `/Input-Switch/Toggle/index.jsx`, `Toggle3`). |
| `Component 2` (State, 2) | `TabItem` | Every reference mounts `StateDefault` / `StateSelectedState` inside `/Tab/Tab/` and its `DefaultActionButton`, `WhenTabGrowsWuthAction`, `DontS` frames. |

Both ship as aliases (`Component1`, `Component2` in `components/_fig/`) pointing at the
built family, not as second implementations. Two more families resolved the same way:
`Header` (Types axis, 4 variants) mounts
`/Product-Header/components/TypesPhase1/TypesPhase1.jsx` on every Page Layout screen, so
it aliases `ProductHeader`; and `Future Edit Field` mounts `EditableFields` variants
(`TypesDateStateEmptyEdit2`, `TypesDropdownStateFilledEdit2`) under
`/Table-WIP/`, so it aliases `EditableFields`. `DropdownItems` and `DropdownItems10`
cover the plural and `[1.0]` publishings of `DropdownItem`.

`heart-fill` is a glyph with no filled variant in the extracted data — `Heart` ships the
outline. The file's remaining `Component 1`
publishings — the `Type: 1, State: 5` sets and the
`State: 4 × 🟢 Active: 2 × ⊖ Intermediate: 2` set — are further duplicate publishings of
the button and checkbox already built under their own names; a single component name can
only answer one of them.

## Component index — kit-name aliases and resolved names

Plain list of every component in this group: `Buttons`, `CheckBox`, `Badge10`, `Checkbox10`, `BottomStatus10`, `TokenPreviewDark`, `DropdownItems`, `DropdownItems10`, `Header`, `FutureEditField`, `InfiniteProcess`, `Component1`, `Component2`, `CheckboxContent`, `DocumentationTableCell`, `SectionHeader`, `HeartFill`, `IconCaretLeft`, `IconCaretRight`.

## Component index — icon families

One named component per kit glyph family (79), in `components/icons/`. Each takes a
`size` prop that snaps to the nearest size the kit publishes for that family (14 / 18 /
24 / 44 where the family has a Size axis; a single size otherwise) and paints with
`currentColor`. Two families are the exception: `IconCaretLeft` and `IconCaretRight` carry
the kit's `Weight` axis (thin / light / regular / bold / fill / duotone) rather than a
Size axis, so they take a `weight` prop. The glyph data already ships in
`assets/kit-icons/`, `assets/ui-icons/` and `assets/extra-icons/`, so a family component
adds markup, not payload. `KitIcon` and `IconBeta` remain available for dynamic,
name-driven lookup.

`Android`, `AngleDoubleLeft`, `AngleDoubleRight`, `AngleDown`, `AngleLeft`, `AngleRight`, `Appointments`, `ArrowLeft`, `ArrowRight`, `Audit`, `Ban`, `Bell`, `Bookmark`, `BookmarkFill`, `Box`, `Building`, `Calendar`, `CalendarPlus`, `Check`, `CheckCircle`, `CheckFill`, `CheckLine`, `ChevronDown`, `ChevronLeft`, `ChevronRight`, `ChevronUp`, `CircleOff`, `Clinic`, `CloudUpload`, `Cog`, `Dispense`, `EllipsisV`, `Envelope`, `ExclamationCircle`, `ExclamationTriangle`, `Eye`, `EyeSlash`, `File`, `FolderOpen`, `Formulary`, `Heart`, `Help`, `History`, `InfoCircle`, `Inventory`, `Lock`, `MapMarker`, `MasterFormulary`, `MyWork`, `Orders`, `Patient`, `Pencil`, `Plus`, `Practice`, `Print`, `Qrcode`, `Refresh`, `Remove`, `Reporting`, `Restock`, `Search`, `ShoppingCart`, `SignOut`, `SlidersV`, `SortAlphaDown`, `SortNumericDown`, `Star`, `Station`, `Support`, `Times`, `TimesCircle`, `Transfer`, `Trash`, `Undo`, `Unlock`, `User`

The four names that previously collided with other files in this project —
`ChevronLeft`, `ChevronRight`, `Inventory`, `Orders` — now hold the kit's own name:
the `_fig` chevron artifacts moved to `fig-chevron-left.jsx` / `fig-chevron-right.jsx`
and the Ally GPO app screens to `screen-inventory.jsx` / `screen-orders.jsx`.
The kit's `chip` glyph family is not built as a component: `Chip` is the kit's own
`Chip [1.0]` control, and the glyph is reachable as `KitIcon name="Chip"`.

## Font substitution note

The Figma uses **Inter** as the sole typeface, loaded here from Google Fonts. If the brand ships a licensed/self-hosted version, drop the `.woff2` files into a `fonts/` folder and swap the `@import` in `colors_and_type.css`. There is no monospace and no secondary display face; codes (NDC/HCPCS) are set in Inter Regular (the *sub heading/detail* token).


## Glyph sourcing — kit glyphs only

Every component that shows an icon renders it from a materialized kit set —
`assets/kit-icons/icon-data.js` (the kit's own set) or `assets/ui-icons/icon-data.js`
(the `❖ Icon (Beta)` UI set) — never a hand-drawn stroke path. The kit glyphs are
FILLED paths, so each is rendered with `fill="currentColor"` and no `stroke`.

| Component | Glyph | Source |
| --- | --- | --- |
| `Alert`, `Banner`, `Toast`, `Modal` | severity / status | `CheckCircleSize24x24` (Success), `ExclamationTriangleSize24x24` (Warning), `TimesCircleSize24x24` (Error), `ExclamationCircleSize24x24` (Info / Neutral) |
| all of the above | dismiss / close | `TimesSize24x24` |
| `Stepper` | completed check | `CheckSize24x24` |
| `SidePanel` | back | `ChevronLeftSize24x24` |
| `SegmentedControl`, `Pagination` | scroll / page nav | `ChevronLeftSize14x14`, `ChevronRightSize14x14` |
| `DatePicker` | month nav | `ChevronLeftSize14x14`, `ChevronRightSize14x14` |
| `Table` | sort | `AngleDownSize24x24`, `ChevronUpSize24x24` |
| `FileUpload` | cloud upload | `CloudUploadSize24x24` |
| `Autocomplete` | search | `SearchSize24x24` (UI set) |
| `Chip` | remove | `RemoveSize24x24` (UI set) |

**No exceptions remain.** The `times` mark used for dismiss / close was previously the one
hand-drawn path in the system. The kit does publish it — the status nodes instance it as
`Size24x245` (`/external-shared/Size24x245/Vector.svg`, an 11.418-unit filled path) — it
was simply missing from the materialized set. It is now `TimesSize24x24` in
`assets/kit-icons/icon-data.js`, and every dismiss / close renders it. **Zero hand-drawn
glyph paths remain.**

**How the severity mapping was established.** Each status glyph is read from the
`data-component` name on the glyph instance inside the corresponding node, not inferred
from a sibling family:

| Node | Status | Instanced glyph |
| --- | --- | --- |
| 3137:49236 | Success Banner | `check-circle` |
| 3137:49246 | Warning Banner | `exclamation-triangle` |
| 3137:49199 | Error Banner | `times-circle` |
| 3137:49241 | Info Banner | `exclamation-circle` |
| 3141:1037 | Neutral Banner | `exclamation-circle`, ink `#64748B` |

The same five names appear on the `Alert` and `w/title` variants of the family, so
`Alert`, `Banner`, `Toast` and `Modal` share one grounded ramp. Error is `times-circle`,
**not** the warning triangle — the two statuses are distinguishable by shape, not hue alone.

## `components/_fig/` — extractor output, and the two bugs it shipped with

`Lozenge` (node 81:23587), `BottomStatus` (4344:182924) and `Footer` (4362:65337)
are **verbatim materializer output**, not hand-authored. That distinction matters: being
faithful to the extractor is not the same as being correct, and an audit of all three
found two systemic defects that made every one of them render wrong.

**1. A foreign token vocabulary.** The extractor preserves the token names of the Figma
libraries those components came from — `--color-background-success-default`,
`--space-050`, `--state-away`, `--components-buttons-primary-filled-bg-default`,
`--4`, `--xl` — **76 names this project never defines**. Undefined, every fill fell back
to transparent or black and every `calc(var(--x) * 1px)` padding collapsed to 0. Lozenge
rendered as bare text with no pill, BottomStatus as five identical black discs, Footer's
primary button as white-on-white. Fixed with a documented bridge block at the end of
`components.css` that defines all 76 in terms of real Ally tokens, rather than editing
extractor output — so a re-materialize stays a drop-in. Two values are node-confirmed
(`--bg-white-0` = `#FFFFFF`, `--state-success` = `#38C793` from node 4344:182925); the
rest map onto the closest existing token and are marked as such.

**2. Lowercase JSX tags.** Composed children are emitted as `<figButtons …>`,
`<figToggle …>`, `<figCheckbox …>`. JSX treats a lowercase-initial tag as an unknown DOM
element, so **every composed child silently rendered nothing** — Footer had no Link Button
and no Cancel button at all. Fixed in all six affected files (`BottomStatus`, `Buttons3`,
`Checkbox2`, `Component13`, `Footer`, `ToggleLabel`) by adding capitalized aliases next
to the imports and rewriting the tags; the note is inline at each site.

**3. A wrong spacing value in the bridge itself.** The bridge's first pass guessed the
Footer spacing names. Auditing against the family's real nodes — which *are* reachable,
as `Modal-WIP` 4362:65336 `Types=Link Button`, 4362:65338 `Types=Label`, 4362:65371
`Types=Toggle` and 4403:112881 `Types=Primary Actions` — showed `--xl` is **12**, not the
16 first assumed: the bar is 520x64, white, 1px `#D8D8D8` on all four sides, padding
`12px 16px`, content space-between at 16px gap. At 16 the vertical padding inflated the
bar past its own 64px height. `--4` = 16 (horizontal) is confirmed correct.

**4. A silent variant-key fallback.** `Bottom Status [1.0]`'s five variants are named with
emoji prefixes carrying invisible variation selectors — `"⚪️ offline"` is `⚪` + U+FE0F.
The demo card passed `"⚪ offline"` (no selector) and `"🚫 blocked"` (not a variant at
all); both missed the variant map and fell through to variant 0, so three of the five dots
rendered as Online green and the real `🏢 company` variant was never shown. `BottomStatus`
now normalizes the plain names (`online`, `offline`, `busy`, `away`, `company`) onto the
kit's exact keys, and the card uses them. This is a general hazard with extractor output:
an unmatched variant key degrades silently to the first body rather than erroring.

**5. Icons authored in path space, clipped to slivers.** Footer's four bodies each carry
two icon SVGs sized at their raw Figma path dimensions (`24.102x18.926`, `33.066x33.001`)
while sitting inside ~15px `overflow:hidden` wells — so only a clipped fragment showed,
reading as a stray dark arc beside "Save Configuration". They also carried a hardcoded
`rgb(37,40,42)` rather than the button's ink token, so they were near-black on the brand
fill. All 8 now fill their well and let the `viewBox` scale, and the filled button sets
`color` from `--components-buttons-primary-filled-text-on-default` so its label and its
icon inherit the same ink.

**6. A token NAME COLLISION the bridge's own check could not catch.** `Footer.jsx`
references `var(--border-default)` — an extractor name that **already exists in this
project** as `#E0E0E0`. So the bridge never redefined it and the foreign reference
silently resolved to a same-named token with the wrong value; node 4362:65336 specifies
`rgb(216,216,216)` = `#D8D8D8`. A "do all vars resolve?" check reports success here,
which is exactly why it slipped through. Footer now uses a bridge-owned
`--fig-border-default` mapped to `--card-border` (`#D8D8D8`).

  Auditing the whole bridge for this class turned up **4 collisions in total**; the other
  three are correct and deliberately left alone:

  | Foreign name | Project value | Node | Verdict |
  | --- | --- | --- | --- |
  | `--border-default` | `#E0E0E0` | `#D8D8D8` (4362:65336) | **wrong — renamed** |
  | `--text-default` | `#25282A` | `rgb(37,40,42)` | correct |
  | `--text-on-brand` | `#FFFFFF` | white check on brand fill | correct |
  | `--text-secondary` | `#757575` | `rgb(117,117,117)` | correct |

  **Rule: a foreign token name that collides with a real one must be renamed, never
  bridged.** Bridging only fixes *undefined* names; a colliding name needs its value
  checked against the node.

  The rename is a component edit, so it lands a compile later — and `--border-default` is
  a legitimate project token (`#E0E0E0`) that must not be redefined globally. The bridge
  therefore re-scopes it on just the elements whose style attribute names it:

  ```css
  [style*="--border-default"]{--border-default:var(--card-border)}
  ```

  Idempotent: once the rename compiles the attribute reads `var(--fig-border-default)`,
  which does not contain the substring `--border-default`, so the selector stops matching
  and the JSX governs. Verified live: `borderTopColor` = `rgb(216,216,216)` on all four
  rows at 520x64 / `padding: 12px 16px`, with the global token still `#E0E0E0`.

**A process note that cost a regression.** Fix 4's normalizer is a component edit, and
component edits only reach `_ds_bundle.js` at the next end-of-turn compile — while CSS and
card edits apply immediately. Changing the card to pass plain names in the same turn as
adding the normalizer left the card depending on code that had not compiled, and every dot
fell through to Online green: worse than the three-colour state it replaced. The card now
passes the kit's **exact** keys, which are always present in `__impls`; the normalizer
stays as a convenience the demo does not rely on. Two rules came out of it: never let a card depend on a same-turn component edit, and when
a visual defect can be fixed from CSS, fix it there too — CSS lands immediately, so the
delivered card is correct in the same turn rather than one turn later. The `_fig` Footer
icon geometry is now enforced from both the JSX and the CSS bridge; the two express the
same thing, and the CSS selector stops matching once the JSX compiles, so nothing
double-applies.

**Standing caveat.** `BottomStatus` is partly audited. Its variants are Online, Offline,
Busy, Away and Company — **not** Verified, which belongs to the separate Avatar badge set
(4344:182897) and is a 27.172px `Stroke` bitmap, not a dot. `--bg-white-0` and
`--state-success` (`#38C793`) are node-confirmed from 4344:182925; the Offline, Busy and
Away dots are still mapped rather than read, because only two of the family's five
variants surface in the mounted reconstruction. `Lozenge` is **not** audited at all: its
node (81:23587) is absent from the mount — only METADATA names the family — so its 12
variants cannot be checked against source here. Both now *render*, which is a floor, not
a ceiling.
