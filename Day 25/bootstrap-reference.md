# Bootstrap 5.3 Components Reference

Class names are for stable 5.3.x. The 6.0 alpha may differ.

## Setup

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.9/dist/css/bootstrap.min.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.9/dist/js/bootstrap.bundle.min.js"></script>
```

The JS bundle is needed for modals, dropdowns, collapse, tabs, toasts.

---

## Grid

12 columns. Breakpoints: `sm` 576, `md` 768, `lg` 992, `xl` 1200, `xxl` 1400 px. Columns stack below their breakpoint.

```html
<div class="container">
  <div class="row g-2">
    <div class="col-12 col-md-4">One</div>
    <div class="col-6 col-md-4">Two</div>
    <div class="col-6 col-md-4">Three</div>
  </div>
  <div class="row">
    <div class="col">Equal</div>
    <div class="col">Equal</div>
    <div class="col-5">Fixed 5/12</div>
  </div>
</div>
```

- `container` fixed width, `container-fluid` full width
- `g-*` gap between columns, `offset-md-2` push a column

## Typography

```html
<h1 class="display-5">Display</h1>
<p class="lead">Larger intro paragraph</p>
<p>Text with <strong>bold</strong>, <em>italic</em>, <mark>mark</mark>, <code>code</code>.</p>
<blockquote class="blockquote"><p>A quote.</p></blockquote>
```

## Buttons

```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-danger">Danger</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-light">Light</button>
<button class="btn btn-dark">Dark</button>
<button class="btn btn-link">Link</button>

<button class="btn btn-outline-primary">Outline</button>
<button class="btn btn-primary btn-lg">Large</button>
<button class="btn btn-primary btn-sm">Small</button>
<button class="btn btn-primary" disabled>Disabled</button>

<div class="btn-group" role="group">
  <button class="btn btn-outline-primary active">Left</button>
  <button class="btn btn-outline-primary">Middle</button>
  <button class="btn btn-outline-primary">Right</button>
</div>
```

## Forms

```html
<form>
  <div class="mb-3">
    <label for="email" class="form-label">Email</label>
    <input type="email" class="form-control" id="email" placeholder="name@example.com">
    <div class="form-text">We'll never share your email.</div>
  </div>

  <select class="form-select mb-3">
    <option>One</option>
    <option>Two</option>
  </select>

  <input type="range" class="form-range mb-3">

  <div class="form-check">
    <input class="form-check-input" type="checkbox" id="chk">
    <label class="form-check-label" for="chk">Checkbox</label>
  </div>
  <div class="form-check">
    <input class="form-check-input" type="radio" name="r" id="r1" checked>
    <label class="form-check-label" for="r1">Radio</label>
  </div>
  <div class="form-check form-switch mb-3">
    <input class="form-check-input" type="checkbox" role="switch" id="sw">
    <label class="form-check-label" for="sw">Switch</label>
  </div>

  <!-- Floating label -->
  <div class="form-floating mb-3">
    <input type="text" class="form-control" id="fl" placeholder="Floating">
    <label for="fl">Floating label</label>
  </div>

  <!-- Input group -->
  <div class="input-group mb-3">
    <span class="input-group-text">@</span>
    <input type="text" class="form-control" placeholder="Username">
    <button class="btn btn-outline-secondary" type="button">Go</button>
  </div>

  <!-- Validation -->
  <input type="text" class="form-control is-invalid">
  <div class="invalid-feedback">Validation message.</div>

  <button class="btn btn-primary mt-3" type="submit">Submit</button>
</form>
```

## Cards

```html
<div class="card" style="width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
  <div class="card-footer text-body-secondary">Footer</div>
</div>

<!-- Colored card -->
<div class="card text-bg-dark">
  <div class="card-body">Dark card</div>
</div>
```

## Navbar

```html
<nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Brand</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
            data-bs-target="#nav" aria-controls="nav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="nav">
      <ul class="navbar-nav me-auto">
        <li class="nav-item"><a class="nav-link active" href="#">Home</a></li>
        <li class="nav-item"><a class="nav-link" href="#">About</a></li>
      </ul>
      <form class="d-flex" role="search">
        <input class="form-control me-2" type="search" placeholder="Search">
        <button class="btn btn-outline-success" type="submit">Search</button>
      </form>
    </div>
  </div>
</nav>
```

- `navbar-expand-lg`: collapses below `lg`
- `fixed-top` / `sticky-top`: pin to the top

## Tabs and pills

```html
<ul class="nav nav-tabs" role="tablist">
  <li class="nav-item" role="presentation">
    <button class="nav-link active" data-bs-toggle="tab" data-bs-target="#tab-a" type="button" role="tab">One</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" data-bs-toggle="tab" data-bs-target="#tab-b" type="button" role="tab">Two</button>
  </li>
</ul>
<div class="tab-content p-3">
  <div class="tab-pane fade show active" id="tab-a" role="tabpanel">Content one</div>
  <div class="tab-pane fade" id="tab-b" role="tabpanel">Content two</div>
</div>
```

Swap `nav-tabs` for `nav-pills` for pill style.

## Alerts

```html
<div class="alert alert-success" role="alert">Success</div>
<div class="alert alert-warning" role="alert">Warning</div>
<div class="alert alert-danger alert-dismissible fade show" role="alert">
  Dismissible
  <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
</div>
```

Colors: `primary secondary success danger warning info light dark`.

## Badges

```html
<span class="badge text-bg-primary">Primary</span>
<span class="badge rounded-pill text-bg-danger">Pill</span>

<button class="btn btn-primary position-relative">
  Inbox
  <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">99+</span>
</button>
```

## Modal

```html
<button class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#myModal">Open modal</button>

<div class="modal fade" id="myModal" tabindex="-1" aria-labelledby="myModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="myModalLabel">Title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">Body text.</div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save</button>
      </div>
    </div>
  </div>
</div>
```

## Dropdown

```html
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
    Menu
  </button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated</a></li>
  </ul>
</div>
```

## Accordion

```html
<div class="accordion" id="acc">
  <div class="accordion-item">
    <h2 class="accordion-header">
      <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#acc1">Item 1</button>
    </h2>
    <div id="acc1" class="accordion-collapse collapse show" data-bs-parent="#acc">
      <div class="accordion-body">Body one.</div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#acc2">Item 2</button>
    </h2>
    <div id="acc2" class="accordion-collapse collapse" data-bs-parent="#acc">
      <div class="accordion-body">Body two.</div>
    </div>
  </div>
</div>
```

## List group

```html
<ul class="list-group">
  <li class="list-group-item active">Active</li>
  <li class="list-group-item">Item</li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    With badge <span class="badge text-bg-primary rounded-pill">14</span>
  </li>
  <li class="list-group-item disabled">Disabled</li>
</ul>
```

## Tables

```html
<div class="table-responsive">
  <table class="table table-striped table-hover align-middle">
    <thead class="table-dark">
      <tr><th>#</th><th>Name</th><th>Role</th></tr>
    </thead>
    <tbody>
      <tr><td>1</td><td>Ada</td><td>Engineer</td></tr>
      <tr class="table-warning"><td>2</td><td>Grace</td><td>Admiral</td></tr>
    </tbody>
  </table>
</div>
```

## Spinner, progress, toast

```html
<div class="spinner-border text-primary" role="status">
  <span class="visually-hidden">Loading...</span>
</div>

<div class="progress" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar progress-bar-striped" style="width: 60%">60%</div>
</div>

<div class="toast-container position-fixed bottom-0 end-0 p-3">
  <div id="myToast" class="toast" role="alert" aria-live="assertive" aria-atomic="true">
    <div class="toast-header">
      <strong class="me-auto">Toast</strong>
      <button type="button" class="btn-close" data-bs-dismiss="toast"></button>
    </div>
    <div class="toast-body">Hello!</div>
  </div>
</div>
<script>
  // Toasts must be shown with JS
  bootstrap.Toast.getOrCreateInstance(document.getElementById('myToast')).show();
</script>
```

## Utilities cheat table

| Purpose | Classes |
|---|---|
| Spacing (0-5) | `m-3` `mt-2` `px-4` `py-1` `mx-auto` `gap-2` |
| Display | `d-none` `d-block` `d-flex` `d-md-none` |
| Flex | `flex-row` `flex-column` `justify-content-between` `align-items-center` |
| Text | `text-center` `text-end` `fw-bold` `fs-4` `text-primary` `text-body-secondary` |
| Background | `bg-primary` `bg-light` `bg-body-tertiary` |
| Borders | `border` `border-0` `rounded` `rounded-pill` `rounded-circle` |
| Sizing | `w-100` `w-50` `h-100` `vh-100` |
| Position | `position-relative` `position-absolute` `fixed-top` `sticky-top` |
| Shadow | `shadow-sm` `shadow` `shadow-lg` |

Spacing format: `{property}{sides}-{breakpoint}-{size}`. `m`/`p` = margin/padding; sides `t b s e x y` (blank = all); size 0-5 or `auto`. Example: `mt-md-3`.

```html
<div class="d-flex justify-content-between align-items-center p-3 bg-primary text-white rounded shadow-sm">
  <span class="fw-bold">Left</span>
  <span>Right</span>
</div>
```
