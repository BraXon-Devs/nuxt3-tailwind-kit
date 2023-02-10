# Dropdown

Dropdown component based on Headless UI `Listbox`. Support multiple dropdownion.

## Basic Usage

Use `<Dropdown />` component to create dropdown and `<DropdownItem />` component to add dropdown item.

::live-preview
  ::dropdown-demos-basic
::

::code-block

```vue
<template>
  <Dropdown>
    <DropdownItem>Item 1</DropdownItem>
    <DropdownItem>Item 2</DropdownItem>
    <DropdownItem>Item 3</DropdownItem>
    <DropdownItem divider />
    <DropdownItem>Item 5</DropdownItem>
    <DropdownItem>Item 6</DropdownItem>
  </Dropdown>
</template>
```

::

## Right Placement

Use `right` prop to place the dropdown to the right.

::live-preview
  ::dropdown-demos-right
::

::code-block

```vue
<template>
  <Dropdown right>
    <DropdownItem>Item 1</DropdownItem>
    <DropdownItem>Item 2</DropdownItem>
    <DropdownItem>Item 3</DropdownItem>
    <DropdownItem divider />
    <DropdownItem>Item 5</DropdownItem>
    <DropdownItem>Item 6</DropdownItem>
  </Dropdown>
</template>
```

::

## Custom Activator

Use `<DropdownButton />` component to create custom dropdown activator. You can also render it as another component like `Button` via `as` prop.

::live-preview
  ::dropdown-demos-custom-activator
::

::code-block

```vue
<script setup lang="ts">
const Button = resolveComponent('Button')
</script>

<template>
  <Dropdown>
    <template #activator>
      <DropdownButton :as="Button" color="primary">
        My Dropdown
      </DropdownButton>
    </template>
    <DropdownItem>Item 1</DropdownItem>
    <DropdownItem>Item 2</DropdownItem>
    <DropdownItem>Item 3</DropdownItem>
    <DropdownItem divider />
    <DropdownItem>Item 5</DropdownItem>
    <DropdownItem>Item 6</DropdownItem>
  </Dropdown>
</template>
```

::

## Props

| Prop | Type | Default | Description |
| ---- | ---- | ------- | ----------- |
| modelValue | `boolean` | `false` | The value of the model. |
| btnProps | `Record<string, any>` | `{ variant: 'secondary' }` | Props for the button component. |
| label | `string` | `'Options'` | The label for the button component. |
| right | `boolean` | `false` | Specifies whether to align the dropdown to the right. |
| items | `DropdownItemProps[]` | `[]` | An array of items to display in the dropdown. |

## Events

None.

## Slots

### activator

The `activator` slot allows you to customize the activator component that triggers the dropdown. The activator component is typically a button or an icon, and is used to open and close the dropdown.

By using the `activator` slot, you have complete control over the appearance and behavior of the activator component. You can use any valid Vue component, including custom components, as the activator.

Here's an example of how to use the `activator` slot:

```vue
<template>
  <Dropdown>
    <template #activator>
      <Button color="primary">
        Custom Activator
      </Button>
    </template>
  </Dropdown>
</template>
```

## Types

```ts
export interface DropdownProps {
  modelValue: boolean
  btnProps: any
  label: string
  right: boolean
  items?: DropdownItemProps[]
}

export interface DropdownItemProps {
  text: string
  to?: string
  href?: string
  icon?: string
  newTab?: boolean
}
```