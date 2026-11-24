# Bootstrap 5.3.9 Class Reference (CDN build)

Every class in `bootstrap.min.css` 5.3.9, extracted from the CSS itself.

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.9/dist/css/bootstrap.min.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.9/dist/js/bootstrap.bundle.min.js"></script>
```

**`{bp}`** = a breakpoint: `sm` (>=576px), `md` (>=768), `lg` (>=992), `xl` (>=1200), `xxl` (>=1400). Example: `d-{bp}-none` means `d-sm-none`, `d-md-none`, etc.

Classes starting with `bs-` are internal (set by JS), and `*-bs-*` custom properties are not classes. Component JS (modal, dropdown, collapse, carousel, tooltip...) needs the bundle script.

## Contents

- [Layout & grid](#layout--grid)
- [Display, flex & alignment](#display-flex--alignment)
- [Spacing](#spacing)
- [Sizing & position](#sizing--position)
- [Typography & text](#typography--text)
- [Colors, backgrounds & borders](#colors-backgrounds--borders)
- [Buttons & forms](#buttons--forms)
- [Navigation](#navigation)
- [Content components](#content-components)
- [Overlays & feedback](#overlays--feedback)
- [Visibility & helpers](#visibility--helpers)
- [Other](#other)

## Layout & grid

Containers, rows, columns, gutters, offsets, ordering.

**col** (30): `col` `col-1` `col-10` `col-11` `col-12` `col-2` `col-3` `col-4` `col-5` `col-6` `col-7` `col-8` `col-9` `col-auto` `col-form-label` `col-form-label-{bp}` `col-{bp}` `col-{bp}-1` `col-{bp}-10` `col-{bp}-11` `col-{bp}-12` `col-{bp}-2` `col-{bp}-3` `col-{bp}-4` `col-{bp}-5` `col-{bp}-6` `col-{bp}-7` `col-{bp}-8` `col-{bp}-9` `col-{bp}-auto`

**column** (12): `column-gap-0` `column-gap-1` `column-gap-2` `column-gap-3` `column-gap-4` `column-gap-5` `column-gap-{bp}-0` `column-gap-{bp}-1` `column-gap-{bp}-2` `column-gap-{bp}-3` `column-gap-{bp}-4` `column-gap-{bp}-5`

**container** (3): `container` `container-fluid` `container-{bp}`

**g** (12): `g-0` `g-1` `g-2` `g-3` `g-4` `g-5` `g-{bp}-0` `g-{bp}-1` `g-{bp}-2` `g-{bp}-3` `g-{bp}-4` `g-{bp}-5`

**gx** (12): `gx-0` `gx-1` `gx-2` `gx-3` `gx-4` `gx-5` `gx-{bp}-0` `gx-{bp}-1` `gx-{bp}-2` `gx-{bp}-3` `gx-{bp}-4` `gx-{bp}-5`

**gy** (12): `gy-0` `gy-1` `gy-2` `gy-3` `gy-4` `gy-5` `gy-{bp}-0` `gy-{bp}-1` `gy-{bp}-2` `gy-{bp}-3` `gy-{bp}-4` `gy-{bp}-5`

**offset** (23): `offset-1` `offset-10` `offset-11` `offset-2` `offset-3` `offset-4` `offset-5` `offset-6` `offset-7` `offset-8` `offset-9` `offset-{bp}-0` `offset-{bp}-1` `offset-{bp}-10` `offset-{bp}-11` `offset-{bp}-2` `offset-{bp}-3` `offset-{bp}-4` `offset-{bp}-5` `offset-{bp}-6` `offset-{bp}-7` `offset-{bp}-8` `offset-{bp}-9`

**order** (16): `order-0` `order-1` `order-2` `order-3` `order-4` `order-5` `order-first` `order-last` `order-{bp}-0` `order-{bp}-1` `order-{bp}-2` `order-{bp}-3` `order-{bp}-4` `order-{bp}-5` `order-{bp}-first` `order-{bp}-last`

**row** (27): `row` `row-cols-1` `row-cols-2` `row-cols-3` `row-cols-4` `row-cols-5` `row-cols-6` `row-cols-auto` `row-cols-{bp}-1` `row-cols-{bp}-2` `row-cols-{bp}-3` `row-cols-{bp}-4` `row-cols-{bp}-5` `row-cols-{bp}-6` `row-cols-{bp}-auto` `row-gap-0` `row-gap-1` `row-gap-2` `row-gap-3` `row-gap-4` `row-gap-5` `row-gap-{bp}-0` `row-gap-{bp}-1` `row-gap-{bp}-2` `row-gap-{bp}-3` `row-gap-{bp}-4` `row-gap-{bp}-5`


## Display, flex & alignment

Show/hide, flexbox, alignment helpers.

**align** (40): `align-baseline` `align-bottom` `align-content-around` `align-content-between` `align-content-center` `align-content-end` `align-content-start` `align-content-stretch` `align-content-{bp}-around` `align-content-{bp}-between` `align-content-{bp}-center` `align-content-{bp}-end` `align-content-{bp}-start` `align-content-{bp}-stretch` `align-items-baseline` `align-items-center` `align-items-end` `align-items-start` `align-items-stretch` `align-items-{bp}-baseline` `align-items-{bp}-center` `align-items-{bp}-end` `align-items-{bp}-start` `align-items-{bp}-stretch` `align-middle` `align-self-auto` `align-self-baseline` `align-self-center` `align-self-end` `align-self-start` `align-self-stretch` `align-self-{bp}-auto` `align-self-{bp}-baseline` `align-self-{bp}-center` `align-self-{bp}-end` `align-self-{bp}-start` `align-self-{bp}-stretch` `align-text-bottom` `align-text-top` `align-top`

**clearfix** (1): `clearfix`

**d** (33): `d-block` `d-flex` `d-grid` `d-inline` `d-inline-block` `d-inline-flex` `d-inline-grid` `d-none` `d-print-block` `d-print-flex` `d-print-grid` `d-print-inline` `d-print-inline-block` `d-print-inline-flex` `d-print-inline-grid` `d-print-none` `d-print-table` `d-print-table-cell` `d-print-table-row` `d-table` `d-table-cell` `d-table-row` `d-{bp}-block` `d-{bp}-flex` `d-{bp}-grid` `d-{bp}-inline` `d-{bp}-inline-block` `d-{bp}-inline-flex` `d-{bp}-inline-grid` `d-{bp}-none` `d-{bp}-table` `d-{bp}-table-cell` `d-{bp}-table-row`

**display** (6): `display-1` `display-2` `display-3` `display-4` `display-5` `display-6`

**flex** (24): `flex-column` `flex-column-reverse` `flex-fill` `flex-grow-0` `flex-grow-1` `flex-nowrap` `flex-row` `flex-row-reverse` `flex-shrink-0` `flex-shrink-1` `flex-wrap` `flex-wrap-reverse` `flex-{bp}-column` `flex-{bp}-column-reverse` `flex-{bp}-fill` `flex-{bp}-grow-0` `flex-{bp}-grow-1` `flex-{bp}-nowrap` `flex-{bp}-row` `flex-{bp}-row-reverse` `flex-{bp}-shrink-0` `flex-{bp}-shrink-1` `flex-{bp}-wrap` `flex-{bp}-wrap-reverse`

**float** (6): `float-end` `float-none` `float-start` `float-{bp}-end` `float-{bp}-none` `float-{bp}-start`

**hstack** (1): `hstack`

**justify** (12): `justify-content-around` `justify-content-between` `justify-content-center` `justify-content-end` `justify-content-evenly` `justify-content-start` `justify-content-{bp}-around` `justify-content-{bp}-between` `justify-content-{bp}-center` `justify-content-{bp}-end` `justify-content-{bp}-evenly` `justify-content-{bp}-start`

**vstack** (1): `vstack`


## Spacing

m = margin, p = padding. Sides: t b s e x y (blank = all). Sizes 0-5, margin also auto. Format: {m|p}{side}-{size}, e.g. mt-3, px-md-4.

**gap** (12): `gap-0` `gap-1` `gap-2` `gap-3` `gap-4` `gap-5` `gap-{bp}-0` `gap-{bp}-1` `gap-{bp}-2` `gap-{bp}-3` `gap-{bp}-4` `gap-{bp}-5`

**m** (14): `m-0` `m-1` `m-2` `m-3` `m-4` `m-5` `m-auto` `m-{bp}-0` `m-{bp}-1` `m-{bp}-2` `m-{bp}-3` `m-{bp}-4` `m-{bp}-5` `m-{bp}-auto`

**mb** (14): `mb-0` `mb-1` `mb-2` `mb-3` `mb-4` `mb-5` `mb-auto` `mb-{bp}-0` `mb-{bp}-1` `mb-{bp}-2` `mb-{bp}-3` `mb-{bp}-4` `mb-{bp}-5` `mb-{bp}-auto`

**me** (14): `me-0` `me-1` `me-2` `me-3` `me-4` `me-5` `me-auto` `me-{bp}-0` `me-{bp}-1` `me-{bp}-2` `me-{bp}-3` `me-{bp}-4` `me-{bp}-5` `me-{bp}-auto`

**ms** (14): `ms-0` `ms-1` `ms-2` `ms-3` `ms-4` `ms-5` `ms-auto` `ms-{bp}-0` `ms-{bp}-1` `ms-{bp}-2` `ms-{bp}-3` `ms-{bp}-4` `ms-{bp}-5` `ms-{bp}-auto`

**mt** (14): `mt-0` `mt-1` `mt-2` `mt-3` `mt-4` `mt-5` `mt-auto` `mt-{bp}-0` `mt-{bp}-1` `mt-{bp}-2` `mt-{bp}-3` `mt-{bp}-4` `mt-{bp}-5` `mt-{bp}-auto`

**mx** (14): `mx-0` `mx-1` `mx-2` `mx-3` `mx-4` `mx-5` `mx-auto` `mx-{bp}-0` `mx-{bp}-1` `mx-{bp}-2` `mx-{bp}-3` `mx-{bp}-4` `mx-{bp}-5` `mx-{bp}-auto`

**my** (14): `my-0` `my-1` `my-2` `my-3` `my-4` `my-5` `my-auto` `my-{bp}-0` `my-{bp}-1` `my-{bp}-2` `my-{bp}-3` `my-{bp}-4` `my-{bp}-5` `my-{bp}-auto`

**p** (12): `p-0` `p-1` `p-2` `p-3` `p-4` `p-5` `p-{bp}-0` `p-{bp}-1` `p-{bp}-2` `p-{bp}-3` `p-{bp}-4` `p-{bp}-5`

**pb** (12): `pb-0` `pb-1` `pb-2` `pb-3` `pb-4` `pb-5` `pb-{bp}-0` `pb-{bp}-1` `pb-{bp}-2` `pb-{bp}-3` `pb-{bp}-4` `pb-{bp}-5`

**pe** (14): `pe-0` `pe-1` `pe-2` `pe-3` `pe-4` `pe-5` `pe-auto` `pe-none` `pe-{bp}-0` `pe-{bp}-1` `pe-{bp}-2` `pe-{bp}-3` `pe-{bp}-4` `pe-{bp}-5`

**ps** (12): `ps-0` `ps-1` `ps-2` `ps-3` `ps-4` `ps-5` `ps-{bp}-0` `ps-{bp}-1` `ps-{bp}-2` `ps-{bp}-3` `ps-{bp}-4` `ps-{bp}-5`

**pt** (12): `pt-0` `pt-1` `pt-2` `pt-3` `pt-4` `pt-5` `pt-{bp}-0` `pt-{bp}-1` `pt-{bp}-2` `pt-{bp}-3` `pt-{bp}-4` `pt-{bp}-5`

**px** (12): `px-0` `px-1` `px-2` `px-3` `px-4` `px-5` `px-{bp}-0` `px-{bp}-1` `px-{bp}-2` `px-{bp}-3` `px-{bp}-4` `px-{bp}-5`

**py** (12): `py-0` `py-1` `py-2` `py-3` `py-4` `py-5` `py-{bp}-0` `py-{bp}-1` `py-{bp}-2` `py-{bp}-3` `py-{bp}-4` `py-{bp}-5`


## Sizing & position

Width, height, ratios, positioning, z-index, overflow.

**bottom** (3): `bottom-0` `bottom-100` `bottom-50`

**end** (3): `end-0` `end-100` `end-50`

**fixed** (2): `fixed-bottom` `fixed-top`

**h** (5): `h-100` `h-25` `h-50` `h-75` `h-auto`

**mh** (1): `mh-100`

**min** (2): `min-vh-100` `min-vw-100`

**mw** (1): `mw-100`

**object** (10): `object-fit-contain` `object-fit-cover` `object-fit-fill` `object-fit-none` `object-fit-scale` `object-fit-{bp}-contain` `object-fit-{bp}-cover` `object-fit-{bp}-fill` `object-fit-{bp}-none` `object-fit-{bp}-scale`

**overflow** (12): `overflow-auto` `overflow-hidden` `overflow-scroll` `overflow-visible` `overflow-x-auto` `overflow-x-hidden` `overflow-x-scroll` `overflow-x-visible` `overflow-y-auto` `overflow-y-hidden` `overflow-y-scroll` `overflow-y-visible`

**position** (5): `position-absolute` `position-fixed` `position-relative` `position-static` `position-sticky`

**ratio** (5): `ratio` `ratio-16x9` `ratio-1x1` `ratio-21x9` `ratio-4x3`

**start** (3): `start-0` `start-100` `start-50`

**sticky** (4): `sticky-bottom` `sticky-top` `sticky-{bp}-bottom` `sticky-{bp}-top`

**top** (3): `top-0` `top-100` `top-50`

**translate** (3): `translate-middle` `translate-middle-x` `translate-middle-y`

**vh** (1): `vh-100`

**vw** (1): `vw-100`

**w** (5): `w-100` `w-25` `w-50` `w-75` `w-auto`

**z** (5): `z-0` `z-1` `z-2` `z-3` `z-n1`


## Typography & text

Headings, display sizes, font weight/size/style, alignment, wrapping.

**blockquote** (2): `blockquote` `blockquote-footer`

**figure** (3): `figure` `figure-caption` `figure-img`

**font** (1): `font-monospace`

**fs** (6): `fs-1` `fs-2` `fs-3` `fs-4` `fs-5` `fs-6`

**fst** (2): `fst-italic` `fst-normal`

**fw** (7): `fw-bold` `fw-bolder` `fw-light` `fw-lighter` `fw-medium` `fw-normal` `fw-semibold`

**h1** (1): `h1`

**h2** (1): `h2`

**h3** (1): `h3`

**h4** (1): `h4`

**h5** (1): `h5`

**h6** (1): `h6`

**initialism** (1): `initialism`

**lead** (1): `lead`

**lh** (3): `lh-1` `lh-base` `lh-{bp}`

**link** (46): `link-body-emphasis` `link-danger` `link-dark` `link-info` `link-light` `link-offset-1` `link-offset-1-hover` `link-offset-2` `link-offset-2-hover` `link-offset-3` `link-offset-3-hover` `link-opacity-10` `link-opacity-10-hover` `link-opacity-100` `link-opacity-100-hover` `link-opacity-25` `link-opacity-25-hover` `link-opacity-50` `link-opacity-50-hover` `link-opacity-75` `link-opacity-75-hover` `link-primary` `link-secondary` `link-success` `link-underline` `link-underline-danger` `link-underline-dark` `link-underline-info` `link-underline-light` `link-underline-opacity-0` `link-underline-opacity-0-hover` `link-underline-opacity-10` `link-underline-opacity-10-hover` `link-underline-opacity-100` `link-underline-opacity-100-hover` `link-underline-opacity-25` `link-underline-opacity-25-hover` `link-underline-opacity-50` `link-underline-opacity-50-hover` `link-underline-opacity-75` `link-underline-opacity-75-hover` `link-underline-primary` `link-underline-secondary` `link-underline-success` `link-underline-warning` `link-warning`

**list** (18): `list-group` `list-group-flush` `list-group-horizontal` `list-group-horizontal-{bp}` `list-group-item` `list-group-item-action` `list-group-item-danger` `list-group-item-dark` `list-group-item-info` `list-group-item-light` `list-group-item-primary` `list-group-item-secondary` `list-group-item-success` `list-group-item-warning` `list-group-numbered` `list-inline` `list-inline-item` `list-unstyled`

**mark** (1): `mark`

**small** (1): `small`

**text** (54): `text-bg-danger` `text-bg-dark` `text-bg-info` `text-bg-light` `text-bg-primary` `text-bg-secondary` `text-bg-success` `text-bg-warning` `text-black` `text-black-50` `text-body` `text-body-emphasis` `text-body-secondary` `text-body-tertiary` `text-break` `text-capitalize` `text-center` `text-danger` `text-danger-emphasis` `text-dark` `text-dark-emphasis` `text-decoration-line-through` `text-decoration-none` `text-decoration-underline` `text-end` `text-info` `text-info-emphasis` `text-light` `text-light-emphasis` `text-lowercase` `text-muted` `text-nowrap` `text-opacity-100` `text-opacity-25` `text-opacity-50` `text-opacity-75` `text-primary` `text-primary-emphasis` `text-reset` `text-secondary` `text-secondary-emphasis` `text-start` `text-success` `text-success-emphasis` `text-truncate` `text-uppercase` `text-warning` `text-warning-emphasis` `text-white` `text-white-50` `text-wrap` `text-{bp}-center` `text-{bp}-end` `text-{bp}-start`

**user** (3): `user-select-all` `user-select-auto` `user-select-none`


## Colors, backgrounds & borders

Theme colors: primary secondary success danger warning info light dark. Plus body, white, black, transparent.

**bg** (28): `bg-black` `bg-body` `bg-body-secondary` `bg-body-tertiary` `bg-danger` `bg-danger-subtle` `bg-dark` `bg-dark-subtle` `bg-gradient` `bg-info` `bg-info-subtle` `bg-light` `bg-light-subtle` `bg-opacity-10` `bg-opacity-100` `bg-opacity-25` `bg-opacity-50` `bg-opacity-75` `bg-primary` `bg-primary-subtle` `bg-secondary` `bg-secondary-subtle` `bg-success` `bg-success-subtle` `bg-transparent` `bg-warning` `bg-warning-subtle` `bg-white`

**border** (38): `border` `border-0` `border-1` `border-2` `border-3` `border-4` `border-5` `border-black` `border-bottom` `border-bottom-0` `border-danger` `border-danger-subtle` `border-dark` `border-dark-subtle` `border-end` `border-end-0` `border-info` `border-info-subtle` `border-light` `border-light-subtle` `border-opacity-10` `border-opacity-100` `border-opacity-25` `border-opacity-50` `border-opacity-75` `border-primary` `border-primary-subtle` `border-secondary` `border-secondary-subtle` `border-start` `border-start-0` `border-success` `border-success-subtle` `border-top` `border-top-0` `border-warning` `border-warning-subtle` `border-white`

**focus** (9): `focus-ring` `focus-ring-danger` `focus-ring-dark` `focus-ring-info` `focus-ring-light` `focus-ring-primary` `focus-ring-secondary` `focus-ring-success` `focus-ring-warning`

**opacity** (5): `opacity-0` `opacity-100` `opacity-25` `opacity-50` `opacity-75`

**rounded** (45): `rounded` `rounded-0` `rounded-1` `rounded-2` `rounded-3` `rounded-4` `rounded-5` `rounded-bottom` `rounded-bottom-0` `rounded-bottom-1` `rounded-bottom-2` `rounded-bottom-3` `rounded-bottom-4` `rounded-bottom-5` `rounded-bottom-circle` `rounded-bottom-pill` `rounded-circle` `rounded-end` `rounded-end-0` `rounded-end-1` `rounded-end-2` `rounded-end-3` `rounded-end-4` `rounded-end-5` `rounded-end-circle` `rounded-end-pill` `rounded-pill` `rounded-start` `rounded-start-0` `rounded-start-1` `rounded-start-2` `rounded-start-3` `rounded-start-4` `rounded-start-5` `rounded-start-circle` `rounded-start-pill` `rounded-top` `rounded-top-0` `rounded-top-1` `rounded-top-2` `rounded-top-3` `rounded-top-4` `rounded-top-5` `rounded-top-circle` `rounded-top-pill`

**shadow** (3): `shadow` `shadow-none` `shadow-{bp}`


## Buttons & forms

Buttons, form controls, input groups, validation.

**btn** (26): `btn` `btn-check` `btn-close` `btn-close-white` `btn-danger` `btn-dark` `btn-group` `btn-group-vertical` `btn-group-{bp}` `btn-info` `btn-light` `btn-link` `btn-outline-danger` `btn-outline-dark` `btn-outline-info` `btn-outline-light` `btn-outline-primary` `btn-outline-secondary` `btn-outline-success` `btn-outline-warning` `btn-primary` `btn-secondary` `btn-success` `btn-toolbar` `btn-warning` `btn-{bp}`

**form** (16): `form-check` `form-check-inline` `form-check-input` `form-check-label` `form-check-reverse` `form-control` `form-control-color` `form-control-plaintext` `form-control-{bp}` `form-floating` `form-label` `form-range` `form-select` `form-select-{bp}` `form-switch` `form-text`

**input** (3): `input-group` `input-group-text` `input-group-{bp}`

**invalid** (2): `invalid-feedback` `invalid-tooltip`

**is** (2): `is-invalid` `is-valid`

**valid** (2): `valid-feedback` `valid-tooltip`

**was** (1): `was-validated`


## Navigation

Nav, navbar, tabs, pills, breadcrumb, pagination, offcanvas.

**breadcrumb** (2): `breadcrumb` `breadcrumb-item`

**nav** (8): `nav` `nav-fill` `nav-item` `nav-justified` `nav-link` `nav-pills` `nav-tabs` `nav-underline`

**navbar** (11): `navbar` `navbar-brand` `navbar-collapse` `navbar-dark` `navbar-expand` `navbar-expand-{bp}` `navbar-nav` `navbar-nav-scroll` `navbar-text` `navbar-toggler` `navbar-toggler-icon`

**offcanvas** (10): `offcanvas` `offcanvas-backdrop` `offcanvas-body` `offcanvas-bottom` `offcanvas-end` `offcanvas-header` `offcanvas-start` `offcanvas-title` `offcanvas-top` `offcanvas-{bp}`

**page** (2): `page-item` `page-link`

**pagination** (2): `pagination` `pagination-{bp}`


## Content components

Cards, lists, tables, images, accordion, carousel.

**accordion** (7): `accordion` `accordion-body` `accordion-button` `accordion-collapse` `accordion-flush` `accordion-header` `accordion-item`

**badge** (1): `badge`

**card** (15): `card` `card-body` `card-footer` `card-group` `card-header` `card-header-pills` `card-header-tabs` `card-img` `card-img-bottom` `card-img-overlay` `card-img-top` `card-link` `card-subtitle` `card-text` `card-title`

**carousel** (15): `carousel` `carousel-caption` `carousel-control-next` `carousel-control-next-icon` `carousel-control-prev` `carousel-control-prev-icon` `carousel-dark` `carousel-fade` `carousel-indicators` `carousel-inner` `carousel-item` `carousel-item-end` `carousel-item-next` `carousel-item-prev` `carousel-item-start`

**img** (2): `img-fluid` `img-thumbnail`

**placeholder** (5): `placeholder` `placeholder-glow` `placeholder-wave` `placeholder-xs` `placeholder-{bp}`

**progress** (5): `progress` `progress-bar` `progress-bar-animated` `progress-bar-striped` `progress-stacked`

**spinner** (4): `spinner-border` `spinner-border-{bp}` `spinner-grow` `spinner-grow-{bp}`

**table** (19): `table` `table-active` `table-bordered` `table-borderless` `table-danger` `table-dark` `table-group-divider` `table-hover` `table-info` `table-light` `table-primary` `table-responsive` `table-responsive-{bp}` `table-secondary` `table-striped` `table-striped-columns` `table-success` `table-warning` `table-{bp}`


## Overlays & feedback

Modals, dropdowns, tooltips, popovers, toasts, alerts.

**alert** (12): `alert` `alert-danger` `alert-dark` `alert-dismissible` `alert-heading` `alert-info` `alert-light` `alert-link` `alert-primary` `alert-secondary` `alert-success` `alert-warning`

**bs** (10): `bs-popover-auto` `bs-popover-bottom` `bs-popover-end` `bs-popover-start` `bs-popover-top` `bs-tooltip-auto` `bs-tooltip-bottom` `bs-tooltip-end` `bs-tooltip-start` `bs-tooltip-top`

**dropdown** (14): `dropdown` `dropdown-center` `dropdown-divider` `dropdown-header` `dropdown-item` `dropdown-item-text` `dropdown-menu` `dropdown-menu-dark` `dropdown-menu-end` `dropdown-menu-start` `dropdown-menu-{bp}-end` `dropdown-menu-{bp}-start` `dropdown-toggle` `dropdown-toggle-split`

**dropend** (1): `dropend`

**dropstart** (1): `dropstart`

**dropup** (2): `dropup` `dropup-center`

**modal** (14): `modal` `modal-backdrop` `modal-body` `modal-content` `modal-dialog` `modal-dialog-centered` `modal-dialog-scrollable` `modal-footer` `modal-fullscreen` `modal-fullscreen-{bp}-down` `modal-header` `modal-static` `modal-title` `modal-{bp}`

**popover** (4): `popover` `popover-arrow` `popover-body` `popover-header`

**toast** (4): `toast` `toast-body` `toast-container` `toast-header`

**tooltip** (3): `tooltip` `tooltip-arrow` `tooltip-inner`


## Visibility & helpers

Screen-reader helpers, stretched links, visibility, state classes.

**active** (1): `active`

**bi** (1): `bi`

**caption** (1): `caption-top`

**collapse** (2): `collapse` `collapse-horizontal`

**collapsed** (1): `collapsed`

**collapsing** (1): `collapsing`

**disabled** (1): `disabled`

**fade** (1): `fade`

**has** (1): `has-validation`

**invisible** (1): `invisible`

**show** (1): `show`

**showing** (1): `showing`

**stretched** (1): `stretched-link`

**tab** (2): `tab-content` `tab-pane`

**visible** (1): `visible`

**visually** (2): `visually-hidden` `visually-hidden-focusable`

**vr** (1): `vr`


## Other

Uncategorized.

**hiding** (1): `hiding`

**icon** (2): `icon-link` `icon-link-hover`

**pointer** (1): `pointer-event`


---
1073 class patterns (breakpoint variants collapsed with `{bp}`).
