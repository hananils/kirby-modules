# Kirby Modules

Easily build modular Kirby websites.

## What is a module?

A module is a regular page, differentiated from other pages by being inside a modules container.
This approach makes it possible to use pages as modules without sacrificing regular subpages:

```
📄 Page
  📄 Subpage A
  📄 Subpage B
  🗂 Modules
    📄 Module A
    📄 Module B
```

## Modules section

The modules section adds some features to the core pages section: 

1. Every blueprint starting with `module.` is available to create.
2. The module blueprint title is displayed in the info.
3. The parent is set to the modules container.
4. The link to the modules container in the headline is disabled.
5. Small style adjustments.

Using the modules section on a page will automatically trigger a built-in hook that creates the `modules` container page.

```yml
sections:
  modules:
    type: modules
```

## Module blueprint

By adding `extends: module/changeTemplate` to the options of your module blueprints, every blueprint starting with `module.` is available to change to.

```yml
options:
  extends: module/changeTemplate
```

## Option

By default, the `module.text` blueprint will be the default. You can set another blueprint in your `site/config/config.php`:

```php
return [
  'medienbaecker.modules' => [
      'default' => 'module.text'
  ]
];
```