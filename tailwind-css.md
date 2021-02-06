# Tailwind CSS

- [Tailwind CSS](#tailwind-css)
  - [Tools/Plugins](#toolsplugins)
  - [Starters/Examples](#startersexamples)
  - [Resources](#resources)
  - [Remembering all the classes](#remembering-all-the-classes)
  - [Library size](#library-size)
  - [Fixing crazy tag salad](#fixing-crazy-tag-salad)
    - [Utility classes](#utility-classes)
  - [Using CSS](#using-css)

## Tools/Plugins
https://color.tailwindow.com
- [tailwindcss-dropdown](https://github.com/estevanmaito/tailwindcss-dropdown)
  - Create accessible, JavaScript free dropdowns with Tailwind CSS
- [tailwind-plugin-font-inter](https://github.com/imsus/tailwind-plugin-font-inter)
  - TailwindCSS Plugin to integrate with Inter UI Typeface
- [tailwindcss-toggle](https://github.com/saraElsanan/tailwindcss-toggle)
  - tailwindcss plugin for toggles
- [__tailwindcss-container-sizes__](https://github.com/Log1x/tailwindcss-container-sizes)
  - Simple Tailwind plugin to generate container sizes.
- [tailwindcss-mobile-precision](https://github.com/robksawyer/tailwindcss-mobile-precision)
  - A collection of add on media queries that allow you to make precision layouts for specific mobile (Yeah, tablet too!) devices.
- [__debug screens__](https://github.com/jorenvanhee/tailwindcss-debug-screens)
  -  Adds a component that shows the currently active screen (responsive breakpoint).
- [tailwindcss-animations](https://github.com/benface/tailwindcss-animations)
  - Tailwind CSS plugin to generate animation utilities
- [tailwindcss-interaction-variants](https://github.com/benface/tailwindcss-interaction-variants)
  - Tailwind CSS plugin to add some missing interaction state variants: checked, group-focus-within, group-active, group-visited, group-disabled, hocus (hover & focus), group-hocus, can-hover, and no-hover
- [tailwindcss/typography](https://github.com/tailwindcss/typography)
  - Official Tailwindcss typography tool

## Starters/Examples

- [__tailblocks__](https://mertjf.github.io/tailblocks)
- [sailui/ui](https://github.com/sailui/ui)
- [tailwindo/component](https://github.com/tailwindow/component)
- [__creative tim starters__](https://www.creative-tim.com/learning-lab/tailwind-starter-kit/presentation)
- [__tailwind components__](https://tailwindcomponents.com)
- [Stitches](https://stitches.hyperyolo.com/)
- [__Rainbow__](https://rainbow.otovo.com/core/typography)

## Resources

- [awesome tailwind](https://project-awesome.org/aniftyco/awesome-tailwindcss)

## Remembering all the classes

Most make sense imo and they are also very similar to bootstraps utility classes and some overlap.

[vscode extension](https://github.com/bradlc/vscode-tailwindcss)

## Library size

https://tailwindcss.com/docs/controlling-file-size

## Fixing crazy tag salad

One example can be found [in the docs](https://tailwindcss.com/components/buttons/), but here is another:

### Utility classes

```html
<div class="max-w-sm rounded overflow-hidden shadow-lg mx-auto my-8">
  <img class="w-full" src="https://tailwindcss.com/img/card-top.jpg" alt="Sunset in the mountains">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">The Coldest Sunset</div>
    <p class="text-gray-600 text-base">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
    </p>
  </div>
  <div class="px-6 py-4">
    <span class="inline-block bg-gray-100 rounded-full px-3 py-1 text-sm font-semibold text-gray-600 mr-2">#photography</span>
    <span class="inline-block bg-gray-100 rounded-full px-3 py-1 text-sm font-semibold text-gray-600 mr-2">#travel</span>
    <span class="inline-block bg-gray-100 rounded-full px-3 py-1 text-sm font-semibold text-gray-600">#winter</span>
  </div>
</div>
```

## Using CSS

```html
<div class="card">
  <img class="card-img" src="https://tailwindcss.com/img/card-top.jpg" alt="Sunset in the mountains">
  <div class="card-body">
    <div class="card-header">The Coldest Sunset</div>
    <p class="card-content">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
    </p>
  </div>
  <div class="card-footer">
    <span class="card-footer-item">#photography</span>
    <span class="card-footer-item">#travel</span>
    <span class="card-footer-item">#winter</span>
  </div>
</div>
```

```css
@import "tailwindcss/base";

@import "tailwindcss/components";

@import "tailwindcss/utilities";

.card {
  @apply max-w-sm rounded overflow-hidden shadow-lg mx-auto my-8;
 }

 .card-img {
   @apply w-full;
 }

 .card-body {
   @apply px-6 py-4;
  }

  .card-header {
    @apply font-bold text-xl mb-2;
  }

  .card-content {
    @apply text-gray-600 text-base;
  }
 .card-footer {
   @apply px-6 py-4;
 }

 .card-footer-item {
  @apply inline-block bg-gray-100 rounded-full px-3 py-1 text-sm font-semibold text-gray-600 mr-2;
 }
```
