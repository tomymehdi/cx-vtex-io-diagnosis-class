📢 Use this project, [contribute](https://github.com/vtex-apps/store-components) to it or open issues to help evolve it using [Store Discussion](https://github.com/vtex-apps/store-discussion).

# Product Specifications

![https://img.shields.io/badge/-Deprecated-red](https://img.shields.io/badge/-Deprecated-red)

> :warning: **The Product Specifications block has been deprecated in favor of the [Product Specifications app](https://vtex.io/docs/components/all/vtex.product-specifications/).**
> Although support for this block is still granted, we strongly recommend you to update your store theme with the Product Specification's blocks in order to keep up with the component's evolution.

`ProductSpecifications` is a block that shows the technical [specifications](https://help.vtex.com/tutorial/what-are-fields-or-specifications--2lB4AgibEseceMggKE2k2m) of a product.

![Screen Shot 2019-12-27 at 14 07 30](https://user-images.githubusercontent.com/27777263/71525823-4bd8a380-28b2-11ea-8d5c-7678426ec1ab.png)

## Configuration

1. Import the `vtex.store-components` app to your theme's dependencies in the `manifest.json`;

```json
  "dependencies": {
    "vtex.store-components": "3.x"
  }
```

2. Add the `product-specifications` block to any block below `store.product` (Product template). For example:

```json
  "store.product": {
    "children": [
      "flex-layout.row#product",
    ]
  },
  "flex-layout.row#product": {
    "children": [
      "product-specifications#product"
    ]
  },
   "product-specifications#product": {
    "props": {
      "shoudCollapseOnTabChange": true,
      "collapsible": "desktopOnly"
    }
  },
```

⚠️ The block consumes data from the product-context therefore it should only be used in the store.product block i.e. in the product template.

| Prop name                | Type                                                       | Description                                                                                                            | Default value |
| ------------------------ | ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------- |
| hiddenSpecifications     | `String[]`                                                 | Type names of specifications you want to hide                                                                          | `[]`          |
| visibleSpecifications    | `String[]`                                                 | Type names of specifications you want to appear. Only provide one of `hiddenSpecifications` or `visibleSpecifications` | `[]`          |
| showSpecificationsTab    | `Boolean`                                                  | Choose if you want to show the component with tabs mode                                                                | `false`       |
| shoudCollapseOnTabChange | `Boolean`                                                  | If it should collapse if you change the tab                                                                            | `false`       |
| collapsible              | `mobileOnly`&#124;`desktopOnly`&#124;`always`&#124;`never` | Control when should the content of the specifications be collapsible                                                   | `always`      |

## Customization

In order to apply CSS customizations in this and other blocks, follow the instructions given in the recipe on [Using CSS Handles for store customization](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization).

| CSS Handles                               |
| ----------------------------------------- |
| `specificationsTitle`                     |
| `specificationsTableContainer`            |
| `specificationsTable`                     |
| `specificationsTableBody`                 |
| `specificationsTableHead`                 |
| `specificationsTableRow`                  |
| `specificationsTabsContainer`             |
| `specificationsTab`                       |
| `specificationsTablePropertyHeading`      |
| `specificationsTableSpecificationHeading` |
| `specificationItemProperty[data-specification="{specificationName}"]` |
| `specificationItemSpecifications`         |
