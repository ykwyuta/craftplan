# GraphQL Reference

Craftplan exposes a [GraphQL](https://graphql.org) API at `/api/graphql`. All requests require
a Bearer token; generate one in
[Settings → API Keys](/craftplan/docs/settings/)
(tokens use the `cpk_` prefix).

×
Close menu

#### Introduction

* [Welcome](#introduction)

#### Operations

* ##### [Queries](#group-Operations-Queries)

  + [getBom](#query-getBom)
  + [getBomComponent](#query-getBomComponent)
  + [getCustomer](#query-getCustomer)
  + [getLot](#query-getLot)
  + [getMaterial](#query-getMaterial)
  + [getMovement](#query-getMovement)
  + [getOrder](#query-getOrder)
  + [getOrderItem](#query-getOrderItem)
  + [getProduct](#query-getProduct)
  + [getProductionBatch](#query-getProductionBatch)
  + [getPurchaseOrder](#query-getPurchaseOrder)
  + [getSupplier](#query-getSupplier)
  + [listBomComponents](#query-listBomComponents)
  + [listBoms](#query-listBoms)
  + [listCustomers](#query-listCustomers)
  + [listLots](#query-listLots)
  + [listMaterials](#query-listMaterials)
  + [listMovements](#query-listMovements)
  + [listOrderItems](#query-listOrderItems)
  + [listOrders](#query-listOrders)
  + [listProductionBatches](#query-listProductionBatches)
  + [listProducts](#query-listProducts)
  + [listPurchaseOrders](#query-listPurchaseOrders)
  + [listSuppliers](#query-listSuppliers)
* ##### [Mutations](#group-Operations-Mutations)

  + [createCustomer](#mutation-createCustomer)
  + [createMaterial](#mutation-createMaterial)
  + [createOrder](#mutation-createOrder)
  + [createOrderItem](#mutation-createOrderItem)
  + [createProduct](#mutation-createProduct)
  + [createPurchaseOrder](#mutation-createPurchaseOrder)
  + [createSupplier](#mutation-createSupplier)
  + [destroyCustomer](#mutation-destroyCustomer)
  + [destroyProduct](#mutation-destroyProduct)
  + [updateCustomer](#mutation-updateCustomer)
  + [updateMaterial](#mutation-updateMaterial)
  + [updateOrder](#mutation-updateOrder)
  + [updateOrderItem](#mutation-updateOrderItem)
  + [updateProduct](#mutation-updateProduct)
  + [updatePurchaseOrder](#mutation-updatePurchaseOrder)
  + [updateSupplier](#mutation-updateSupplier)

#### Types

* [Bom](#definition-Bom)
* [BomComponent](#definition-BomComponent)
* [BomComponentFilterId](#definition-BomComponentFilterId)
* [BomComponentFilterInput](#definition-BomComponentFilterInput)
* [BomComponentSortField](#definition-BomComponentSortField)
* [BomComponentSortInput](#definition-BomComponentSortInput)
* [BomFilterId](#definition-BomFilterId)
* [BomFilterInput](#definition-BomFilterInput)
* [BomFilterName](#definition-BomFilterName)
* [BomFilterNotes](#definition-BomFilterNotes)
* [BomFilterStatus](#definition-BomFilterStatus)
* [BomSortField](#definition-BomSortField)
* [BomSortInput](#definition-BomSortInput)
* [Boolean](#definition-Boolean)
* [CreateCustomerInput](#definition-CreateCustomerInput)
* [CreateCustomerResult](#definition-CreateCustomerResult)
* [CreateMaterialInput](#definition-CreateMaterialInput)
* [CreateMaterialResult](#definition-CreateMaterialResult)
* [CreateOrderInput](#definition-CreateOrderInput)
* [CreateOrderItemInput](#definition-CreateOrderItemInput)
* [CreateOrderItemResult](#definition-CreateOrderItemResult)
* [CreateOrderResult](#definition-CreateOrderResult)
* [CreateProductInput](#definition-CreateProductInput)
* [CreateProductResult](#definition-CreateProductResult)
* [CreatePurchaseOrderInput](#definition-CreatePurchaseOrderInput)
* [CreatePurchaseOrderResult](#definition-CreatePurchaseOrderResult)
* [CreateSupplierInput](#definition-CreateSupplierInput)
* [CreateSupplierResult](#definition-CreateSupplierResult)
* [Customer](#definition-Customer)
* [CustomerFilterEmail](#definition-CustomerFilterEmail)
* [CustomerFilterFirstName](#definition-CustomerFilterFirstName)
* [CustomerFilterId](#definition-CustomerFilterId)
* [CustomerFilterInput](#definition-CustomerFilterInput)
* [CustomerFilterLastName](#definition-CustomerFilterLastName)
* [CustomerFilterPhone](#definition-CustomerFilterPhone)
* [CustomerFilterType](#definition-CustomerFilterType)
* [CustomerSortField](#definition-CustomerSortField)
* [CustomerSortInput](#definition-CustomerSortInput)
* [DateTime](#definition-DateTime)
* [Decimal](#definition-Decimal)
* [DestroyCustomerResult](#definition-DestroyCustomerResult)
* [DestroyProductResult](#definition-DestroyProductResult)
* [ID](#definition-ID)
* [Int](#definition-Int)
* [Json](#definition-Json)
* [JsonString](#definition-JsonString)
* [KeysetPageOfBomComponent](#definition-KeysetPageOfBomComponent)
* [KeysetPageOfCustomer](#definition-KeysetPageOfCustomer)
* [KeysetPageOfLot](#definition-KeysetPageOfLot)
* [KeysetPageOfMaterial](#definition-KeysetPageOfMaterial)
* [KeysetPageOfMovement](#definition-KeysetPageOfMovement)
* [KeysetPageOfOrder](#definition-KeysetPageOfOrder)
* [KeysetPageOfOrderItem](#definition-KeysetPageOfOrderItem)
* [KeysetPageOfProduct](#definition-KeysetPageOfProduct)
* [KeysetPageOfProductionBatch](#definition-KeysetPageOfProductionBatch)
* [Lot](#definition-Lot)
* [LotFilterId](#definition-LotFilterId)
* [LotFilterInput](#definition-LotFilterInput)
* [LotSortField](#definition-LotSortField)
* [LotSortInput](#definition-LotSortInput)
* [Material](#definition-Material)
* [MaterialFilterId](#definition-MaterialFilterId)
* [MaterialFilterInput](#definition-MaterialFilterInput)
* [MaterialFilterMaximumStock](#definition-MaterialFilterMaximumStock)
* [MaterialFilterMinimumStock](#definition-MaterialFilterMinimumStock)
* [MaterialFilterName](#definition-MaterialFilterName)
* [MaterialFilterPrice](#definition-MaterialFilterPrice)
* [MaterialFilterSku](#definition-MaterialFilterSku)
* [MaterialFilterUnit](#definition-MaterialFilterUnit)
* [MaterialSortField](#definition-MaterialSortField)
* [MaterialSortInput](#definition-MaterialSortInput)
* [Movement](#definition-Movement)
* [MovementFilterId](#definition-MovementFilterId)
* [MovementFilterInput](#definition-MovementFilterInput)
* [MovementSortField](#definition-MovementSortField)
* [MovementSortInput](#definition-MovementSortInput)
* [MutationError](#definition-MutationError)
* [Order](#definition-Order)
* [OrderCreateItemsInput](#definition-OrderCreateItemsInput)
* [OrderFilterId](#definition-OrderFilterId)
* [OrderFilterInput](#definition-OrderFilterInput)
* [OrderItem](#definition-OrderItem)
* [OrderItemFilterId](#definition-OrderItemFilterId)
* [OrderItemFilterInput](#definition-OrderItemFilterInput)
* [OrderItemSortField](#definition-OrderItemSortField)
* [OrderItemSortInput](#definition-OrderItemSortInput)
* [OrderSortField](#definition-OrderSortField)
* [OrderSortInput](#definition-OrderSortInput)
* [OrderUpdateItemsInput](#definition-OrderUpdateItemsInput)
* [Product](#definition-Product)
* [ProductFilterFeaturedPhoto](#definition-ProductFilterFeaturedPhoto)
* [ProductFilterId](#definition-ProductFilterId)
* [ProductFilterInput](#definition-ProductFilterInput)
* [ProductFilterMaxDailyQuantity](#definition-ProductFilterMaxDailyQuantity)
* [ProductFilterName](#definition-ProductFilterName)
* [ProductFilterPrice](#definition-ProductFilterPrice)
* [ProductFilterSellingAvailability](#definition-ProductFilterSellingAvailability)
* [ProductFilterStatus](#definition-ProductFilterStatus)
* [ProductSortField](#definition-ProductSortField)
* [ProductSortInput](#definition-ProductSortInput)
* [ProductionBatch](#definition-ProductionBatch)
* [ProductionBatchFilterId](#definition-ProductionBatchFilterId)
* [ProductionBatchFilterInput](#definition-ProductionBatchFilterInput)
* [ProductionBatchSortField](#definition-ProductionBatchSortField)
* [ProductionBatchSortInput](#definition-ProductionBatchSortInput)
* [PurchaseOrder](#definition-PurchaseOrder)
* [PurchaseOrderFilterId](#definition-PurchaseOrderFilterId)
* [PurchaseOrderFilterInput](#definition-PurchaseOrderFilterInput)
* [PurchaseOrderSortField](#definition-PurchaseOrderSortField)
* [PurchaseOrderSortInput](#definition-PurchaseOrderSortInput)
* [SortOrder](#definition-SortOrder)
* [String](#definition-String)
* [Supplier](#definition-Supplier)
* [SupplierFilterId](#definition-SupplierFilterId)
* [SupplierFilterInput](#definition-SupplierFilterInput)
* [SupplierSortField](#definition-SupplierSortField)
* [SupplierSortInput](#definition-SupplierSortInput)
* [UpdateCustomerInput](#definition-UpdateCustomerInput)
* [UpdateCustomerResult](#definition-UpdateCustomerResult)
* [UpdateMaterialInput](#definition-UpdateMaterialInput)
* [UpdateMaterialResult](#definition-UpdateMaterialResult)
* [UpdateOrderInput](#definition-UpdateOrderInput)
* [UpdateOrderItemInput](#definition-UpdateOrderItemInput)
* [UpdateOrderItemResult](#definition-UpdateOrderItemResult)
* [UpdateOrderResult](#definition-UpdateOrderResult)
* [UpdateProductInput](#definition-UpdateProductInput)
* [UpdateProductResult](#definition-UpdateProductResult)
* [UpdatePurchaseOrderInput](#definition-UpdatePurchaseOrderInput)
* [UpdatePurchaseOrderResult](#definition-UpdatePurchaseOrderResult)
* [UpdateSupplierInput](#definition-UpdateSupplierInput)
* [UpdateSupplierResult](#definition-UpdateSupplierResult)

All topics

# Craftplan GraphQL API

GraphQL API for Craftplan ERP. All requests require a Bearer token — generate one in Settings → API Keys (tokens use the `cpk_` prefix).

##### Contact

Craftplan

##### API Endpoints

```
http://localhost:4000/api/graphql
```

# Queries

## `getBom`

##### Response

Returns a [`Bom`](#definition-Bom)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getBom($id: ID!) {
  getBom(id: $id) {
    id
    name
    notes
    status
  }
}
```

##### Variables

```
{"id": 4}
```

##### Response

```
{
  "data": {
    "getBom": {
      "id": "4",
      "name": "abc123",
      "notes": "abc123",
      "status": "xyz789"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `getBomComponent`

##### Response

Returns a [`BomComponent`](#definition-BomComponent)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getBomComponent($id: ID!) {
  getBomComponent(id: $id) {
    id
  }
}
```

##### Variables

```
{"id": "4"}
```

##### Response

```
{"data": {"getBomComponent": {"id": "4"}}}
```

[Queries](#group-Operations-Queries)

## `getCustomer`

##### Response

Returns a [`Customer`](#definition-Customer)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getCustomer($id: ID!) {
  getCustomer(id: $id) {
    id
    type
    firstName
    lastName
    email
    phone
    billingAddress
    shippingAddress
  }
}
```

##### Variables

```
{"id": "4"}
```

##### Response

```
{
  "data": {
    "getCustomer": {
      "id": "4",
      "type": "xyz789",
      "firstName": "abc123",
      "lastName": "xyz789",
      "email": "abc123",
      "phone": "abc123",
      "billingAddress": JsonString,
      "shippingAddress": JsonString
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `getLot`

##### Response

Returns a [`Lot`](#definition-Lot)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getLot($id: ID!) {
  getLot(id: $id) {
    id
  }
}
```

##### Variables

```
{"id": "4"}
```

##### Response

```
{"data": {"getLot": {"id": "4"}}}
```

[Queries](#group-Operations-Queries)

## `getMaterial`

##### Response

Returns a [`Material`](#definition-Material)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getMaterial($id: ID!) {
  getMaterial(id: $id) {
    id
    name
    sku
    unit
    price
    minimumStock
    maximumStock
  }
}
```

##### Variables

```
{"id": 4}
```

##### Response

```
{
  "data": {
    "getMaterial": {
      "id": 4,
      "name": "abc123",
      "sku": "xyz789",
      "unit": "abc123",
      "price": Decimal,
      "minimumStock": Decimal,
      "maximumStock": Decimal
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `getMovement`

##### Response

Returns a [`Movement`](#definition-Movement)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getMovement($id: ID!) {
  getMovement(id: $id) {
    id
  }
}
```

##### Variables

```
{"id": "4"}
```

##### Response

```
{"data": {"getMovement": {"id": 4}}}
```

[Queries](#group-Operations-Queries)

## `getOrder`

##### Response

Returns an [`Order`](#definition-Order)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getOrder($id: ID!) {
  getOrder(id: $id) {
    id
  }
}
```

##### Variables

```
{"id": 4}
```

##### Response

```
{"data": {"getOrder": {"id": "4"}}}
```

[Queries](#group-Operations-Queries)

## `getOrderItem`

##### Response

Returns an [`OrderItem`](#definition-OrderItem)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getOrderItem($id: ID!) {
  getOrderItem(id: $id) {
    id
  }
}
```

##### Variables

```
{"id": 4}
```

##### Response

```
{"data": {"getOrderItem": {"id": "4"}}}
```

[Queries](#group-Operations-Queries)

## `getProduct`

##### Response

Returns a [`Product`](#definition-Product)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getProduct($id: ID!) {
  getProduct(id: $id) {
    id
    name
    status
    price
    photos
    featuredPhoto
    sellingAvailability
    maxDailyQuantity
  }
}
```

##### Variables

```
{"id": "4"}
```

##### Response

```
{
  "data": {
    "getProduct": {
      "id": 4,
      "name": "abc123",
      "status": "abc123",
      "price": Decimal,
      "photos": ["abc123"],
      "featuredPhoto": "abc123",
      "sellingAvailability": "xyz789",
      "maxDailyQuantity": 987
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `getProductionBatch`

##### Response

Returns a [`ProductionBatch`](#definition-ProductionBatch)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getProductionBatch($id: ID!) {
  getProductionBatch(id: $id) {
    id
  }
}
```

##### Variables

```
{"id": "4"}
```

##### Response

```
{
  "data": {
    "getProductionBatch": {"id": "4"}
  }
}
```

[Queries](#group-Operations-Queries)

## `getPurchaseOrder`

##### Response

Returns a [`PurchaseOrder`](#definition-PurchaseOrder)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getPurchaseOrder($id: ID!) {
  getPurchaseOrder(id: $id) {
    id
  }
}
```

##### Variables

```
{"id": 4}
```

##### Response

```
{"data": {"getPurchaseOrder": {"id": "4"}}}
```

[Queries](#group-Operations-Queries)

## `getSupplier`

##### Response

Returns a [`Supplier`](#definition-Supplier)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) | The id of the record |

#### Example

##### Query

```
query getSupplier($id: ID!) {
  getSupplier(id: $id) {
    id
  }
}
```

##### Variables

```
{"id": "4"}
```

##### Response

```
{"data": {"getSupplier": {"id": "4"}}}
```

[Queries](#group-Operations-Queries)

## `listBomComponents`

##### Response

Returns a [`KeysetPageOfBomComponent`](#definition-KeysetPageOfBomComponent)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[BomComponentSortInput]`](#definition-BomComponentSortInput) | How to sort the records in the response |
| `filter` - [`BomComponentFilterInput`](#definition-BomComponentFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |

#### Example

##### Query

```
query listBomComponents(
  $sort: [BomComponentSortInput],
  $filter: BomComponentFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int
) {
  listBomComponents(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last
  ) {
    count
    results {
      ...BomComponentFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [BomComponentSortInput],
  "filter": BomComponentFilterInput,
  "first": 123,
  "before": "xyz789",
  "after": "abc123",
  "last": 987
}
```

##### Response

```
{
  "data": {
    "listBomComponents": {
      "count": 123,
      "results": [BomComponent],
      "startKeyset": "abc123",
      "endKeyset": "xyz789"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listBoms`

##### Response

Returns [`[Bom!]!`](#definition-Bom)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[BomSortInput]`](#definition-BomSortInput) | How to sort the records in the response |
| `filter` - [`BomFilterInput`](#definition-BomFilterInput) | A filter to limit the results |
| `productId` - [`ID!`](#definition-ID) |  |

#### Example

##### Query

```
query listBoms(
  $sort: [BomSortInput],
  $filter: BomFilterInput,
  $productId: ID!
) {
  listBoms(
    sort: $sort,
    filter: $filter,
    productId: $productId
  ) {
    id
    name
    notes
    status
  }
}
```

##### Variables

```
{
  "sort": [BomSortInput],
  "filter": BomFilterInput,
  "productId": "4"
}
```

##### Response

```
{
  "data": {
    "listBoms": [
      {
        "id": 4,
        "name": "xyz789",
        "notes": "xyz789",
        "status": "xyz789"
      }
    ]
  }
}
```

[Queries](#group-Operations-Queries)

## `listCustomers`

##### Response

Returns a [`KeysetPageOfCustomer`](#definition-KeysetPageOfCustomer)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[CustomerSortInput]`](#definition-CustomerSortInput) | How to sort the records in the response |
| `filter` - [`CustomerFilterInput`](#definition-CustomerFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |

#### Example

##### Query

```
query listCustomers(
  $sort: [CustomerSortInput],
  $filter: CustomerFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int
) {
  listCustomers(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last
  ) {
    count
    results {
      ...CustomerFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [CustomerSortInput],
  "filter": CustomerFilterInput,
  "first": 987,
  "before": "xyz789",
  "after": "abc123",
  "last": 987
}
```

##### Response

```
{
  "data": {
    "listCustomers": {
      "count": 123,
      "results": [Customer],
      "startKeyset": "xyz789",
      "endKeyset": "xyz789"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listLots`

##### Response

Returns a [`KeysetPageOfLot`](#definition-KeysetPageOfLot)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[LotSortInput]`](#definition-LotSortInput) | How to sort the records in the response |
| `filter` - [`LotFilterInput`](#definition-LotFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |

#### Example

##### Query

```
query listLots(
  $sort: [LotSortInput],
  $filter: LotFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int
) {
  listLots(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last
  ) {
    count
    results {
      ...LotFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [LotSortInput],
  "filter": LotFilterInput,
  "first": 987,
  "before": "xyz789",
  "after": "abc123",
  "last": 123
}
```

##### Response

```
{
  "data": {
    "listLots": {
      "count": 987,
      "results": [Lot],
      "startKeyset": "abc123",
      "endKeyset": "abc123"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listMaterials`

##### Response

Returns a [`KeysetPageOfMaterial`](#definition-KeysetPageOfMaterial)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[MaterialSortInput]`](#definition-MaterialSortInput) | How to sort the records in the response |
| `filter` - [`MaterialFilterInput`](#definition-MaterialFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |

#### Example

##### Query

```
query listMaterials(
  $sort: [MaterialSortInput],
  $filter: MaterialFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int
) {
  listMaterials(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last
  ) {
    count
    results {
      ...MaterialFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [MaterialSortInput],
  "filter": MaterialFilterInput,
  "first": 987,
  "before": "abc123",
  "after": "xyz789",
  "last": 123
}
```

##### Response

```
{
  "data": {
    "listMaterials": {
      "count": 123,
      "results": [Material],
      "startKeyset": "abc123",
      "endKeyset": "abc123"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listMovements`

##### Response

Returns a [`KeysetPageOfMovement`](#definition-KeysetPageOfMovement)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[MovementSortInput]`](#definition-MovementSortInput) | How to sort the records in the response |
| `filter` - [`MovementFilterInput`](#definition-MovementFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |

#### Example

##### Query

```
query listMovements(
  $sort: [MovementSortInput],
  $filter: MovementFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int
) {
  listMovements(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last
  ) {
    count
    results {
      ...MovementFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [MovementSortInput],
  "filter": MovementFilterInput,
  "first": 123,
  "before": "xyz789",
  "after": "xyz789",
  "last": 987
}
```

##### Response

```
{
  "data": {
    "listMovements": {
      "count": 123,
      "results": [Movement],
      "startKeyset": "abc123",
      "endKeyset": "abc123"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listOrderItems`

##### Response

Returns a [`KeysetPageOfOrderItem`](#definition-KeysetPageOfOrderItem)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[OrderItemSortInput]`](#definition-OrderItemSortInput) | How to sort the records in the response |
| `filter` - [`OrderItemFilterInput`](#definition-OrderItemFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |

#### Example

##### Query

```
query listOrderItems(
  $sort: [OrderItemSortInput],
  $filter: OrderItemFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int
) {
  listOrderItems(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last
  ) {
    count
    results {
      ...OrderItemFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [OrderItemSortInput],
  "filter": OrderItemFilterInput,
  "first": 987,
  "before": "abc123",
  "after": "abc123",
  "last": 987
}
```

##### Response

```
{
  "data": {
    "listOrderItems": {
      "count": 123,
      "results": [OrderItem],
      "startKeyset": "abc123",
      "endKeyset": "xyz789"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listOrders`

##### Response

Returns a [`KeysetPageOfOrder`](#definition-KeysetPageOfOrder)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[OrderSortInput]`](#definition-OrderSortInput) | How to sort the records in the response |
| `filter` - [`OrderFilterInput`](#definition-OrderFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |
| `status` - [`[String!]`](#definition-String) |  |
| `paymentStatus` - [`[String!]`](#definition-String) |  |
| `deliveryDateStart` - [`DateTime`](#definition-DateTime) |  |
| `deliveryDateEnd` - [`DateTime`](#definition-DateTime) |  |
| `customerName` - [`String`](#definition-String) |  |
| `productId` - [`ID`](#definition-ID) |  |

#### Example

##### Query

```
query listOrders(
  $sort: [OrderSortInput],
  $filter: OrderFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int,
  $status: [String!],
  $paymentStatus: [String!],
  $deliveryDateStart: DateTime,
  $deliveryDateEnd: DateTime,
  $customerName: String,
  $productId: ID
) {
  listOrders(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last,
    status: $status,
    paymentStatus: $paymentStatus,
    deliveryDateStart: $deliveryDateStart,
    deliveryDateEnd: $deliveryDateEnd,
    customerName: $customerName,
    productId: $productId
  ) {
    count
    results {
      ...OrderFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [OrderSortInput],
  "filter": OrderFilterInput,
  "first": 123,
  "before": "xyz789",
  "after": "xyz789",
  "last": 987,
  "status": ["abc123"],
  "paymentStatus": ["abc123"],
  "deliveryDateStart": "2007-12-03T10:15:30Z",
  "deliveryDateEnd": "2007-12-03T10:15:30Z",
  "customerName": "abc123",
  "productId": 4
}
```

##### Response

```
{
  "data": {
    "listOrders": {
      "count": 987,
      "results": [Order],
      "startKeyset": "xyz789",
      "endKeyset": "abc123"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listProductionBatches`

##### Response

Returns a [`KeysetPageOfProductionBatch`](#definition-KeysetPageOfProductionBatch)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[ProductionBatchSortInput]`](#definition-ProductionBatchSortInput) | How to sort the records in the response |
| `filter` - [`ProductionBatchFilterInput`](#definition-ProductionBatchFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |

#### Example

##### Query

```
query listProductionBatches(
  $sort: [ProductionBatchSortInput],
  $filter: ProductionBatchFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int
) {
  listProductionBatches(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last
  ) {
    count
    results {
      ...ProductionBatchFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [ProductionBatchSortInput],
  "filter": ProductionBatchFilterInput,
  "first": 987,
  "before": "xyz789",
  "after": "xyz789",
  "last": 123
}
```

##### Response

```
{
  "data": {
    "listProductionBatches": {
      "count": 123,
      "results": [ProductionBatch],
      "startKeyset": "xyz789",
      "endKeyset": "abc123"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listProducts`

##### Response

Returns a [`KeysetPageOfProduct`](#definition-KeysetPageOfProduct)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[ProductSortInput]`](#definition-ProductSortInput) | How to sort the records in the response |
| `filter` - [`ProductFilterInput`](#definition-ProductFilterInput) | A filter to limit the results |
| `first` - [`Int`](#definition-Int) | The number of records to return from the beginning. Maximum 250 |
| `before` - [`String`](#definition-String) | Show records before the specified keyset. |
| `after` - [`String`](#definition-String) | Show records after the specified keyset. |
| `last` - [`Int`](#definition-Int) | The number of records to return to the end. Maximum 250 |
| `status` - [`[String!]`](#definition-String) |  |

#### Example

##### Query

```
query listProducts(
  $sort: [ProductSortInput],
  $filter: ProductFilterInput,
  $first: Int,
  $before: String,
  $after: String,
  $last: Int,
  $status: [String!]
) {
  listProducts(
    sort: $sort,
    filter: $filter,
    first: $first,
    before: $before,
    after: $after,
    last: $last,
    status: $status
  ) {
    count
    results {
      ...ProductFragment
    }
    startKeyset
    endKeyset
  }
}
```

##### Variables

```
{
  "sort": [ProductSortInput],
  "filter": ProductFilterInput,
  "first": 123,
  "before": "abc123",
  "after": "xyz789",
  "last": 987,
  "status": ["abc123"]
}
```

##### Response

```
{
  "data": {
    "listProducts": {
      "count": 123,
      "results": [Product],
      "startKeyset": "xyz789",
      "endKeyset": "abc123"
    }
  }
}
```

[Queries](#group-Operations-Queries)

## `listPurchaseOrders`

##### Response

Returns [`[PurchaseOrder!]!`](#definition-PurchaseOrder)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[PurchaseOrderSortInput]`](#definition-PurchaseOrderSortInput) | How to sort the records in the response |
| `filter` - [`PurchaseOrderFilterInput`](#definition-PurchaseOrderFilterInput) | A filter to limit the results |

#### Example

##### Query

```
query listPurchaseOrders(
  $sort: [PurchaseOrderSortInput],
  $filter: PurchaseOrderFilterInput
) {
  listPurchaseOrders(
    sort: $sort,
    filter: $filter
  ) {
    id
  }
}
```

##### Variables

```
{
  "sort": [PurchaseOrderSortInput],
  "filter": PurchaseOrderFilterInput
}
```

##### Response

```
{"data": {"listPurchaseOrders": [{"id": 4}]}}
```

[Queries](#group-Operations-Queries)

## `listSuppliers`

##### Response

Returns [`[Supplier!]!`](#definition-Supplier)

##### Arguments

| Name | Description |
| --- | --- |
| `sort` - [`[SupplierSortInput]`](#definition-SupplierSortInput) | How to sort the records in the response |
| `filter` - [`SupplierFilterInput`](#definition-SupplierFilterInput) | A filter to limit the results |

#### Example

##### Query

```
query listSuppliers(
  $sort: [SupplierSortInput],
  $filter: SupplierFilterInput
) {
  listSuppliers(
    sort: $sort,
    filter: $filter
  ) {
    id
  }
}
```

##### Variables

```
{
  "sort": [SupplierSortInput],
  "filter": SupplierFilterInput
}
```

##### Response

```
{"data": {"listSuppliers": [{"id": 4}]}}
```

# Mutations

## `createCustomer`

##### Response

Returns a [`CreateCustomerResult!`](#definition-CreateCustomerResult)

##### Arguments

| Name | Description |
| --- | --- |
| `input` - [`CreateCustomerInput!`](#definition-CreateCustomerInput) |  |

#### Example

##### Query

```
mutation createCustomer($input: CreateCustomerInput!) {
  createCustomer(input: $input) {
    result {
      ...CustomerFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"input": CreateCustomerInput}
```

##### Response

```
{
  "data": {
    "createCustomer": {
      "result": Customer,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `createMaterial`

##### Response

Returns a [`CreateMaterialResult!`](#definition-CreateMaterialResult)

##### Arguments

| Name | Description |
| --- | --- |
| `input` - [`CreateMaterialInput!`](#definition-CreateMaterialInput) |  |

#### Example

##### Query

```
mutation createMaterial($input: CreateMaterialInput!) {
  createMaterial(input: $input) {
    result {
      ...MaterialFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"input": CreateMaterialInput}
```

##### Response

```
{
  "data": {
    "createMaterial": {
      "result": Material,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `createOrder`

##### Response

Returns a [`CreateOrderResult!`](#definition-CreateOrderResult)

##### Arguments

| Name | Description |
| --- | --- |
| `input` - [`CreateOrderInput!`](#definition-CreateOrderInput) |  |

#### Example

##### Query

```
mutation createOrder($input: CreateOrderInput!) {
  createOrder(input: $input) {
    result {
      ...OrderFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"input": CreateOrderInput}
```

##### Response

```
{
  "data": {
    "createOrder": {
      "result": Order,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `createOrderItem`

##### Response

Returns a [`CreateOrderItemResult!`](#definition-CreateOrderItemResult)

##### Arguments

| Name | Description |
| --- | --- |
| `input` - [`CreateOrderItemInput!`](#definition-CreateOrderItemInput) |  |

#### Example

##### Query

```
mutation createOrderItem($input: CreateOrderItemInput!) {
  createOrderItem(input: $input) {
    result {
      ...OrderItemFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"input": CreateOrderItemInput}
```

##### Response

```
{
  "data": {
    "createOrderItem": {
      "result": OrderItem,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `createProduct`

##### Response

Returns a [`CreateProductResult!`](#definition-CreateProductResult)

##### Arguments

| Name | Description |
| --- | --- |
| `input` - [`CreateProductInput!`](#definition-CreateProductInput) |  |

#### Example

##### Query

```
mutation createProduct($input: CreateProductInput!) {
  createProduct(input: $input) {
    result {
      ...ProductFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"input": CreateProductInput}
```

##### Response

```
{
  "data": {
    "createProduct": {
      "result": Product,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `createPurchaseOrder`

##### Response

Returns a [`CreatePurchaseOrderResult!`](#definition-CreatePurchaseOrderResult)

##### Arguments

| Name | Description |
| --- | --- |
| `input` - [`CreatePurchaseOrderInput!`](#definition-CreatePurchaseOrderInput) |  |

#### Example

##### Query

```
mutation createPurchaseOrder($input: CreatePurchaseOrderInput!) {
  createPurchaseOrder(input: $input) {
    result {
      ...PurchaseOrderFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"input": CreatePurchaseOrderInput}
```

##### Response

```
{
  "data": {
    "createPurchaseOrder": {
      "result": PurchaseOrder,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `createSupplier`

##### Response

Returns a [`CreateSupplierResult!`](#definition-CreateSupplierResult)

##### Arguments

| Name | Description |
| --- | --- |
| `input` - [`CreateSupplierInput!`](#definition-CreateSupplierInput) |  |

#### Example

##### Query

```
mutation createSupplier($input: CreateSupplierInput!) {
  createSupplier(input: $input) {
    result {
      ...SupplierFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"input": CreateSupplierInput}
```

##### Response

```
{
  "data": {
    "createSupplier": {
      "result": Supplier,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `destroyCustomer`

##### Response

Returns a [`DestroyCustomerResult!`](#definition-DestroyCustomerResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

#### Example

##### Query

```
mutation destroyCustomer($id: ID!) {
  destroyCustomer(id: $id) {
    result {
      ...CustomerFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"id": "4"}
```

##### Response

```
{
  "data": {
    "destroyCustomer": {
      "result": Customer,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `destroyProduct`

##### Response

Returns a [`DestroyProductResult!`](#definition-DestroyProductResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

#### Example

##### Query

```
mutation destroyProduct($id: ID!) {
  destroyProduct(id: $id) {
    result {
      ...ProductFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"id": 4}
```

##### Response

```
{
  "data": {
    "destroyProduct": {
      "result": Product,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `updateCustomer`

##### Response

Returns an [`UpdateCustomerResult!`](#definition-UpdateCustomerResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `input` - [`UpdateCustomerInput`](#definition-UpdateCustomerInput) |  |

#### Example

##### Query

```
mutation updateCustomer(
  $id: ID!,
  $input: UpdateCustomerInput
) {
  updateCustomer(
    id: $id,
    input: $input
  ) {
    result {
      ...CustomerFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{
  "id": "4",
  "input": UpdateCustomerInput
}
```

##### Response

```
{
  "data": {
    "updateCustomer": {
      "result": Customer,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `updateMaterial`

##### Response

Returns an [`UpdateMaterialResult!`](#definition-UpdateMaterialResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `input` - [`UpdateMaterialInput`](#definition-UpdateMaterialInput) |  |

#### Example

##### Query

```
mutation updateMaterial(
  $id: ID!,
  $input: UpdateMaterialInput
) {
  updateMaterial(
    id: $id,
    input: $input
  ) {
    result {
      ...MaterialFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{
  "id": "4",
  "input": UpdateMaterialInput
}
```

##### Response

```
{
  "data": {
    "updateMaterial": {
      "result": Material,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `updateOrder`

##### Response

Returns an [`UpdateOrderResult!`](#definition-UpdateOrderResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `input` - [`UpdateOrderInput`](#definition-UpdateOrderInput) |  |

#### Example

##### Query

```
mutation updateOrder(
  $id: ID!,
  $input: UpdateOrderInput
) {
  updateOrder(
    id: $id,
    input: $input
  ) {
    result {
      ...OrderFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"id": 4, "input": UpdateOrderInput}
```

##### Response

```
{
  "data": {
    "updateOrder": {
      "result": Order,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `updateOrderItem`

##### Response

Returns an [`UpdateOrderItemResult!`](#definition-UpdateOrderItemResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `input` - [`UpdateOrderItemInput`](#definition-UpdateOrderItemInput) |  |

#### Example

##### Query

```
mutation updateOrderItem(
  $id: ID!,
  $input: UpdateOrderItemInput
) {
  updateOrderItem(
    id: $id,
    input: $input
  ) {
    result {
      ...OrderItemFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{
  "id": "4",
  "input": UpdateOrderItemInput
}
```

##### Response

```
{
  "data": {
    "updateOrderItem": {
      "result": OrderItem,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `updateProduct`

##### Response

Returns an [`UpdateProductResult!`](#definition-UpdateProductResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `input` - [`UpdateProductInput`](#definition-UpdateProductInput) |  |

#### Example

##### Query

```
mutation updateProduct(
  $id: ID!,
  $input: UpdateProductInput
) {
  updateProduct(
    id: $id,
    input: $input
  ) {
    result {
      ...ProductFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{"id": 4, "input": UpdateProductInput}
```

##### Response

```
{
  "data": {
    "updateProduct": {
      "result": Product,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `updatePurchaseOrder`

##### Response

Returns an [`UpdatePurchaseOrderResult!`](#definition-UpdatePurchaseOrderResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `input` - [`UpdatePurchaseOrderInput`](#definition-UpdatePurchaseOrderInput) |  |

#### Example

##### Query

```
mutation updatePurchaseOrder(
  $id: ID!,
  $input: UpdatePurchaseOrderInput
) {
  updatePurchaseOrder(
    id: $id,
    input: $input
  ) {
    result {
      ...PurchaseOrderFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{
  "id": "4",
  "input": UpdatePurchaseOrderInput
}
```

##### Response

```
{
  "data": {
    "updatePurchaseOrder": {
      "result": PurchaseOrder,
      "errors": [MutationError]
    }
  }
}
```

[Mutations](#group-Operations-Mutations)

## `updateSupplier`

##### Response

Returns an [`UpdateSupplierResult!`](#definition-UpdateSupplierResult)

##### Arguments

| Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `input` - [`UpdateSupplierInput`](#definition-UpdateSupplierInput) |  |

#### Example

##### Query

```
mutation updateSupplier(
  $id: ID!,
  $input: UpdateSupplierInput
) {
  updateSupplier(
    id: $id,
    input: $input
  ) {
    result {
      ...SupplierFragment
    }
    errors {
      ...MutationErrorFragment
    }
  }
}
```

##### Variables

```
{
  "id": "4",
  "input": UpdateSupplierInput
}
```

##### Response

```
{
  "data": {
    "updateSupplier": {
      "result": Supplier,
      "errors": [MutationError]
    }
  }
}
```

# Types

## Bom

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `name` - [`String`](#definition-String) |  |
| `notes` - [`String`](#definition-String) |  |
| `status` - [`String!`](#definition-String) |  |

##### Example

```
{
  "id": 4,
  "name": "abc123",
  "notes": "abc123",
  "status": "abc123"
}
```

[Types](#group-Types)

## BomComponent

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

##### Example

```
{"id": "4"}
```

[Types](#group-Types)

## BomComponentFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": false,
  "eq": 4,
  "notEq": 4,
  "in": ["4"],
  "lessThan": 4,
  "greaterThan": 4,
  "lessThanOrEqual": 4,
  "greaterThanOrEqual": "4"
}
```

[Types](#group-Types)

## BomComponentFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[BomComponentFilterInput!]`](#definition-BomComponentFilterInput) |  |
| `or` - [`[BomComponentFilterInput!]`](#definition-BomComponentFilterInput) |  |
| `not` - [`[BomComponentFilterInput!]`](#definition-BomComponentFilterInput) |  |
| `id` - [`BomComponentFilterId`](#definition-BomComponentFilterId) |  |

##### Example

```
{
  "and": [BomComponentFilterInput],
  "or": [BomComponentFilterInput],
  "not": [BomComponentFilterInput],
  "id": BomComponentFilterId
}
```

[Types](#group-Types)

## BomComponentSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## BomComponentSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`BomComponentSortField!`](#definition-BomComponentSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## BomFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": false,
  "eq": "4",
  "notEq": "4",
  "in": ["4"],
  "lessThan": "4",
  "greaterThan": 4,
  "lessThanOrEqual": "4",
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## BomFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[BomFilterInput!]`](#definition-BomFilterInput) |  |
| `or` - [`[BomFilterInput!]`](#definition-BomFilterInput) |  |
| `not` - [`[BomFilterInput!]`](#definition-BomFilterInput) |  |
| `id` - [`BomFilterId`](#definition-BomFilterId) |  |
| `name` - [`BomFilterName`](#definition-BomFilterName) |  |
| `notes` - [`BomFilterNotes`](#definition-BomFilterNotes) |  |
| `status` - [`BomFilterStatus`](#definition-BomFilterStatus) |  |

##### Example

```
{
  "and": [BomFilterInput],
  "or": [BomFilterInput],
  "not": [BomFilterInput],
  "id": BomFilterId,
  "name": BomFilterName,
  "notes": BomFilterNotes,
  "status": BomFilterStatus
}
```

[Types](#group-Types)

## BomFilterName

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": true,
  "eq": "abc123",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "xyz789",
  "greaterThan": "abc123",
  "lessThanOrEqual": "xyz789",
  "greaterThanOrEqual": "xyz789",
  "like": "xyz789",
  "ilike": "xyz789"
}
```

[Types](#group-Types)

## BomFilterNotes

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "abc123",
  "greaterThan": "abc123",
  "lessThanOrEqual": "abc123",
  "greaterThanOrEqual": "abc123",
  "like": "abc123",
  "ilike": "xyz789"
}
```

[Types](#group-Types)

## BomFilterStatus

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": true,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["abc123"],
  "lessThan": "abc123",
  "greaterThan": "abc123",
  "lessThanOrEqual": "abc123",
  "greaterThanOrEqual": "abc123"
}
```

[Types](#group-Types)

## BomSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |
| `NAME` |  |
| `NOTES` |  |
| `STATUS` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## BomSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`BomSortField!`](#definition-BomSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## Boolean

##### Description

The `Boolean` scalar type represents `true` or `false`.

[Types](#group-Types)

## CreateCustomerInput

##### Fields

| Input Field | Description |
| --- | --- |
| `type` - [`String!`](#definition-String) |  |
| `firstName` - [`String!`](#definition-String) |  |
| `lastName` - [`String!`](#definition-String) |  |
| `email` - [`String`](#definition-String) |  |
| `phone` - [`String`](#definition-String) |  |
| `billingAddress` - [`JsonString`](#definition-JsonString) |  |
| `shippingAddress` - [`JsonString`](#definition-JsonString) |  |

##### Example

```
{
  "type": "xyz789",
  "firstName": "abc123",
  "lastName": "xyz789",
  "email": "abc123",
  "phone": "xyz789",
  "billingAddress": JsonString,
  "shippingAddress": JsonString
}
```

[Types](#group-Types)

## CreateCustomerResult

##### Description

The result of the :create\_customer mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Customer`](#definition-Customer) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Customer,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## CreateMaterialInput

##### Fields

| Input Field | Description |
| --- | --- |
| `name` - [`String!`](#definition-String) |  |
| `sku` - [`String!`](#definition-String) |  |
| `unit` - [`String!`](#definition-String) |  |
| `price` - [`Decimal!`](#definition-Decimal) |  |
| `minimumStock` - [`Decimal`](#definition-Decimal) |  |
| `maximumStock` - [`Decimal`](#definition-Decimal) |  |

##### Example

```
{
  "name": "abc123",
  "sku": "abc123",
  "unit": "abc123",
  "price": Decimal,
  "minimumStock": Decimal,
  "maximumStock": Decimal
}
```

[Types](#group-Types)

## CreateMaterialResult

##### Description

The result of the :create\_material mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Material`](#definition-Material) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Material,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## CreateOrderInput

##### Fields

| Input Field | Description |
| --- | --- |
| `deliveryDate` - [`DateTime!`](#definition-DateTime) |  |
| `invoiceNumber` - [`String`](#definition-String) |  |
| `invoiceStatus` - [`String`](#definition-String) |  |
| `invoicedAt` - [`DateTime`](#definition-DateTime) |  |
| `paymentMethod` - [`String`](#definition-String) |  |
| `discountType` - [`String`](#definition-String) |  |
| `discountValue` - [`Decimal`](#definition-Decimal) |  |
| `deliveryMethod` - [`String`](#definition-String) |  |
| `status` - [`String`](#definition-String) |  |
| `customerId` - [`ID!`](#definition-ID) |  |
| `items` - [`[OrderCreateItemsInput!]`](#definition-OrderCreateItemsInput) |  |

##### Example

```
{
  "deliveryDate": "2007-12-03T10:15:30Z",
  "invoiceNumber": "abc123",
  "invoiceStatus": "xyz789",
  "invoicedAt": "2007-12-03T10:15:30Z",
  "paymentMethod": "abc123",
  "discountType": "xyz789",
  "discountValue": Decimal,
  "deliveryMethod": "xyz789",
  "status": "xyz789",
  "customerId": 4,
  "items": [OrderCreateItemsInput]
}
```

[Types](#group-Types)

## CreateOrderItemInput

##### Fields

| Input Field | Description |
| --- | --- |
| `unitPrice` - [`Decimal!`](#definition-Decimal) |  |
| `quantity` - [`Decimal!`](#definition-Decimal) |  |
| `status` - [`String`](#definition-String) |  |
| `productId` - [`ID!`](#definition-ID) |  |

##### Example

```
{
  "unitPrice": Decimal,
  "quantity": Decimal,
  "status": "abc123",
  "productId": 4
}
```

[Types](#group-Types)

## CreateOrderItemResult

##### Description

The result of the :create\_order\_item mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`OrderItem`](#definition-OrderItem) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": OrderItem,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## CreateOrderResult

##### Description

The result of the :create\_order mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Order`](#definition-Order) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Order,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## CreateProductInput

##### Fields

| Input Field | Description |
| --- | --- |
| `name` - [`String!`](#definition-String) |  |
| `status` - [`String`](#definition-String) |  |
| `price` - [`Decimal!`](#definition-Decimal) |  |
| `sku` - [`String!`](#definition-String) |  |
| `photos` - [`[String!]`](#definition-String) | Array of photo URLs for the product |
| `featuredPhoto` - [`String`](#definition-String) | ID or reference to the featured photo from the photos array |
| `sellingAvailability` - [`String`](#definition-String) | Customer-facing availability: available, preorder, or off |
| `maxDailyQuantity` - [`Int`](#definition-Int) | Optional per-product capacity per day (0 = unlimited) |

##### Example

```
{
  "name": "xyz789",
  "status": "xyz789",
  "price": Decimal,
  "sku": "abc123",
  "photos": ["abc123"],
  "featuredPhoto": "xyz789",
  "sellingAvailability": "xyz789",
  "maxDailyQuantity": 987
}
```

[Types](#group-Types)

## CreateProductResult

##### Description

The result of the :create\_product mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Product`](#definition-Product) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Product,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## CreatePurchaseOrderInput

##### Fields

| Input Field | Description |
| --- | --- |
| `status` - [`String`](#definition-String) |  |
| `orderedAt` - [`DateTime`](#definition-DateTime) |  |
| `supplierId` - [`ID!`](#definition-ID) |  |

##### Example

```
{
  "status": "abc123",
  "orderedAt": "2007-12-03T10:15:30Z",
  "supplierId": "4"
}
```

[Types](#group-Types)

## CreatePurchaseOrderResult

##### Description

The result of the :create\_purchase\_order mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`PurchaseOrder`](#definition-PurchaseOrder) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": PurchaseOrder,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## CreateSupplierInput

##### Fields

| Input Field | Description |
| --- | --- |
| `name` - [`String!`](#definition-String) |  |
| `contactName` - [`String`](#definition-String) |  |
| `contactEmail` - [`String`](#definition-String) |  |
| `contactPhone` - [`String`](#definition-String) |  |
| `notes` - [`String`](#definition-String) |  |

##### Example

```
{
  "name": "xyz789",
  "contactName": "abc123",
  "contactEmail": "abc123",
  "contactPhone": "abc123",
  "notes": "abc123"
}
```

[Types](#group-Types)

## CreateSupplierResult

##### Description

The result of the :create\_supplier mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Supplier`](#definition-Supplier) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Supplier,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## Customer

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `type` - [`String!`](#definition-String) |  |
| `firstName` - [`String!`](#definition-String) |  |
| `lastName` - [`String!`](#definition-String) |  |
| `email` - [`String`](#definition-String) |  |
| `phone` - [`String`](#definition-String) |  |
| `billingAddress` - [`JsonString`](#definition-JsonString) |  |
| `shippingAddress` - [`JsonString`](#definition-JsonString) |  |

##### Example

```
{
  "id": 4,
  "type": "xyz789",
  "firstName": "abc123",
  "lastName": "xyz789",
  "email": "abc123",
  "phone": "abc123",
  "billingAddress": JsonString,
  "shippingAddress": JsonString
}
```

[Types](#group-Types)

## CustomerFilterEmail

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "abc123",
  "notEq": "abc123",
  "in": ["xyz789"],
  "lessThan": "xyz789",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "xyz789",
  "greaterThanOrEqual": "xyz789",
  "like": "xyz789",
  "ilike": "abc123"
}
```

[Types](#group-Types)

## CustomerFilterFirstName

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": true,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "abc123",
  "greaterThan": "abc123",
  "lessThanOrEqual": "xyz789",
  "greaterThanOrEqual": "abc123",
  "like": "xyz789",
  "ilike": "abc123"
}
```

[Types](#group-Types)

## CustomerFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": false,
  "eq": 4,
  "notEq": 4,
  "in": ["4"],
  "lessThan": 4,
  "greaterThan": 4,
  "lessThanOrEqual": 4,
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## CustomerFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[CustomerFilterInput!]`](#definition-CustomerFilterInput) |  |
| `or` - [`[CustomerFilterInput!]`](#definition-CustomerFilterInput) |  |
| `not` - [`[CustomerFilterInput!]`](#definition-CustomerFilterInput) |  |
| `id` - [`CustomerFilterId`](#definition-CustomerFilterId) |  |
| `type` - [`CustomerFilterType`](#definition-CustomerFilterType) |  |
| `firstName` - [`CustomerFilterFirstName`](#definition-CustomerFilterFirstName) |  |
| `lastName` - [`CustomerFilterLastName`](#definition-CustomerFilterLastName) |  |
| `email` - [`CustomerFilterEmail`](#definition-CustomerFilterEmail) |  |
| `phone` - [`CustomerFilterPhone`](#definition-CustomerFilterPhone) |  |

##### Example

```
{
  "and": [CustomerFilterInput],
  "or": [CustomerFilterInput],
  "not": [CustomerFilterInput],
  "id": CustomerFilterId,
  "type": CustomerFilterType,
  "firstName": CustomerFilterFirstName,
  "lastName": CustomerFilterLastName,
  "email": CustomerFilterEmail,
  "phone": CustomerFilterPhone
}
```

[Types](#group-Types)

## CustomerFilterLastName

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["abc123"],
  "lessThan": "xyz789",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "abc123",
  "greaterThanOrEqual": "xyz789",
  "like": "xyz789",
  "ilike": "abc123"
}
```

[Types](#group-Types)

## CustomerFilterPhone

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "abc123",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "abc123",
  "greaterThanOrEqual": "xyz789",
  "like": "xyz789",
  "ilike": "abc123"
}
```

[Types](#group-Types)

## CustomerFilterType

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "xyz789",
  "notEq": "abc123",
  "in": ["xyz789"],
  "lessThan": "xyz789",
  "greaterThan": "abc123",
  "lessThanOrEqual": "abc123",
  "greaterThanOrEqual": "abc123"
}
```

[Types](#group-Types)

## CustomerSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |
| `TYPE` |  |
| `FIRST_NAME` |  |
| `LAST_NAME` |  |
| `EMAIL` |  |
| `PHONE` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## CustomerSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`CustomerSortField!`](#definition-CustomerSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## DateTime

##### Description

The `DateTime` scalar type represents a date and time in the UTC timezone. The DateTime appears in a JSON response as an ISO8601 formatted string, including UTC timezone ("Z"). The parsed date and time string will be converted to UTC if there is an offset.

##### Example

```
"2007-12-03T10:15:30Z"
```

[Types](#group-Types)

## Decimal

##### Description

The `Decimal` scalar type represents signed double-precision fractional values parsed by the `Decimal` library. The Decimal appears in a JSON response as a string to preserve precision.

##### Example

```
Decimal
```

[Types](#group-Types)

## DestroyCustomerResult

##### Description

The result of the :destroy\_customer mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Customer`](#definition-Customer) | The record that was successfully deleted |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Customer,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## DestroyProductResult

##### Description

The result of the :destroy\_product mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Product`](#definition-Product) | The record that was successfully deleted |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Product,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## ID

##### Description

The `ID` scalar type represents a unique identifier, often used to refetch an object or as key for a cache. The ID type appears in a JSON response as a String; however, it is not intended to be human-readable. When expected as an input type, any string (such as `"4"`) or integer (such as `4`) input value will be accepted as an ID.

##### Example

```
"4"
```

[Types](#group-Types)

## Int

##### Description

The `Int` scalar type represents non-fractional signed whole numeric values. Int can represent values between -(2^31) and 2^31 - 1.

##### Example

```
987
```

[Types](#group-Types)

## Json

##### Description

The `Json` scalar type represents arbitrary json string data, represented as UTF-8 character sequences. The Json type is most often used to represent a free-form human-readable json string.

##### Example

```
Json
```

[Types](#group-Types)

## JsonString

##### Description

The `Json` scalar type represents arbitrary json string data, represented as UTF-8 character sequences. The Json type is most often used to represent a free-form human-readable json string.

##### Example

```
JsonString
```

[Types](#group-Types)

## KeysetPageOfBomComponent

##### Description

A keyset page of :bom\_component

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[BomComponent!]`](#definition-BomComponent) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 987,
  "results": [BomComponent],
  "startKeyset": "abc123",
  "endKeyset": "xyz789"
}
```

[Types](#group-Types)

## KeysetPageOfCustomer

##### Description

A keyset page of :customer

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[Customer!]`](#definition-Customer) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 987,
  "results": [Customer],
  "startKeyset": "xyz789",
  "endKeyset": "abc123"
}
```

[Types](#group-Types)

## KeysetPageOfLot

##### Description

A keyset page of :lot

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[Lot!]`](#definition-Lot) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 123,
  "results": [Lot],
  "startKeyset": "abc123",
  "endKeyset": "abc123"
}
```

[Types](#group-Types)

## KeysetPageOfMaterial

##### Description

A keyset page of :material

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[Material!]`](#definition-Material) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 123,
  "results": [Material],
  "startKeyset": "abc123",
  "endKeyset": "abc123"
}
```

[Types](#group-Types)

## KeysetPageOfMovement

##### Description

A keyset page of :movement

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[Movement!]`](#definition-Movement) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 987,
  "results": [Movement],
  "startKeyset": "abc123",
  "endKeyset": "abc123"
}
```

[Types](#group-Types)

## KeysetPageOfOrder

##### Description

A keyset page of :order

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[Order!]`](#definition-Order) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 123,
  "results": [Order],
  "startKeyset": "xyz789",
  "endKeyset": "abc123"
}
```

[Types](#group-Types)

## KeysetPageOfOrderItem

##### Description

A keyset page of :order\_item

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[OrderItem!]`](#definition-OrderItem) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 123,
  "results": [OrderItem],
  "startKeyset": "xyz789",
  "endKeyset": "abc123"
}
```

[Types](#group-Types)

## KeysetPageOfProduct

##### Description

A keyset page of :product

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[Product!]`](#definition-Product) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 123,
  "results": [Product],
  "startKeyset": "xyz789",
  "endKeyset": "abc123"
}
```

[Types](#group-Types)

## KeysetPageOfProductionBatch

##### Description

A keyset page of :production\_batch

##### Fields

| Field Name | Description |
| --- | --- |
| `count` - [`Int`](#definition-Int) | Total count on all pages |
| `results` - [`[ProductionBatch!]`](#definition-ProductionBatch) | The records contained in the page |
| `startKeyset` - [`String`](#definition-String) | The first keyset in the results |
| `endKeyset` - [`String`](#definition-String) | The last keyset in the results |

##### Example

```
{
  "count": 123,
  "results": [ProductionBatch],
  "startKeyset": "xyz789",
  "endKeyset": "abc123"
}
```

[Types](#group-Types)

## Lot

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

##### Example

```
{"id": "4"}
```

[Types](#group-Types)

## LotFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": true,
  "eq": "4",
  "notEq": 4,
  "in": [4],
  "lessThan": 4,
  "greaterThan": "4",
  "lessThanOrEqual": 4,
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## LotFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[LotFilterInput!]`](#definition-LotFilterInput) |  |
| `or` - [`[LotFilterInput!]`](#definition-LotFilterInput) |  |
| `not` - [`[LotFilterInput!]`](#definition-LotFilterInput) |  |
| `id` - [`LotFilterId`](#definition-LotFilterId) |  |

##### Example

```
{
  "and": [LotFilterInput],
  "or": [LotFilterInput],
  "not": [LotFilterInput],
  "id": LotFilterId
}
```

[Types](#group-Types)

## LotSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## LotSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`LotSortField!`](#definition-LotSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## Material

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `name` - [`String!`](#definition-String) |  |
| `sku` - [`String!`](#definition-String) |  |
| `unit` - [`String!`](#definition-String) |  |
| `price` - [`Decimal!`](#definition-Decimal) |  |
| `minimumStock` - [`Decimal`](#definition-Decimal) |  |
| `maximumStock` - [`Decimal`](#definition-Decimal) |  |

##### Example

```
{
  "id": 4,
  "name": "abc123",
  "sku": "abc123",
  "unit": "abc123",
  "price": Decimal,
  "minimumStock": Decimal,
  "maximumStock": Decimal
}
```

[Types](#group-Types)

## MaterialFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": true,
  "eq": 4,
  "notEq": 4,
  "in": [4],
  "lessThan": 4,
  "greaterThan": 4,
  "lessThanOrEqual": "4",
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## MaterialFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[MaterialFilterInput!]`](#definition-MaterialFilterInput) |  |
| `or` - [`[MaterialFilterInput!]`](#definition-MaterialFilterInput) |  |
| `not` - [`[MaterialFilterInput!]`](#definition-MaterialFilterInput) |  |
| `id` - [`MaterialFilterId`](#definition-MaterialFilterId) |  |
| `name` - [`MaterialFilterName`](#definition-MaterialFilterName) |  |
| `sku` - [`MaterialFilterSku`](#definition-MaterialFilterSku) |  |
| `unit` - [`MaterialFilterUnit`](#definition-MaterialFilterUnit) |  |
| `price` - [`MaterialFilterPrice`](#definition-MaterialFilterPrice) |  |
| `minimumStock` - [`MaterialFilterMinimumStock`](#definition-MaterialFilterMinimumStock) |  |
| `maximumStock` - [`MaterialFilterMaximumStock`](#definition-MaterialFilterMaximumStock) |  |

##### Example

```
{
  "and": [MaterialFilterInput],
  "or": [MaterialFilterInput],
  "not": [MaterialFilterInput],
  "id": MaterialFilterId,
  "name": MaterialFilterName,
  "sku": MaterialFilterSku,
  "unit": MaterialFilterUnit,
  "price": MaterialFilterPrice,
  "minimumStock": MaterialFilterMinimumStock,
  "maximumStock": MaterialFilterMaximumStock
}
```

[Types](#group-Types)

## MaterialFilterMaximumStock

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`Decimal`](#definition-Decimal) |  |
| `notEq` - [`Decimal`](#definition-Decimal) |  |
| `in` - [`[Decimal]`](#definition-Decimal) |  |
| `lessThan` - [`Decimal`](#definition-Decimal) |  |
| `greaterThan` - [`Decimal`](#definition-Decimal) |  |
| `lessThanOrEqual` - [`Decimal`](#definition-Decimal) |  |
| `greaterThanOrEqual` - [`Decimal`](#definition-Decimal) |  |

##### Example

```
{
  "isNil": false,
  "eq": Decimal,
  "notEq": Decimal,
  "in": [Decimal],
  "lessThan": Decimal,
  "greaterThan": Decimal,
  "lessThanOrEqual": Decimal,
  "greaterThanOrEqual": Decimal
}
```

[Types](#group-Types)

## MaterialFilterMinimumStock

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`Decimal`](#definition-Decimal) |  |
| `notEq` - [`Decimal`](#definition-Decimal) |  |
| `in` - [`[Decimal]`](#definition-Decimal) |  |
| `lessThan` - [`Decimal`](#definition-Decimal) |  |
| `greaterThan` - [`Decimal`](#definition-Decimal) |  |
| `lessThanOrEqual` - [`Decimal`](#definition-Decimal) |  |
| `greaterThanOrEqual` - [`Decimal`](#definition-Decimal) |  |

##### Example

```
{
  "isNil": false,
  "eq": Decimal,
  "notEq": Decimal,
  "in": [Decimal],
  "lessThan": Decimal,
  "greaterThan": Decimal,
  "lessThanOrEqual": Decimal,
  "greaterThanOrEqual": Decimal
}
```

[Types](#group-Types)

## MaterialFilterName

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "xyz789",
  "notEq": "abc123",
  "in": ["xyz789"],
  "lessThan": "abc123",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "xyz789",
  "greaterThanOrEqual": "abc123",
  "like": "xyz789",
  "ilike": "abc123"
}
```

[Types](#group-Types)

## MaterialFilterPrice

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`Decimal`](#definition-Decimal) |  |
| `notEq` - [`Decimal`](#definition-Decimal) |  |
| `in` - [`[Decimal!]`](#definition-Decimal) |  |
| `lessThan` - [`Decimal`](#definition-Decimal) |  |
| `greaterThan` - [`Decimal`](#definition-Decimal) |  |
| `lessThanOrEqual` - [`Decimal`](#definition-Decimal) |  |
| `greaterThanOrEqual` - [`Decimal`](#definition-Decimal) |  |

##### Example

```
{
  "isNil": false,
  "eq": Decimal,
  "notEq": Decimal,
  "in": [Decimal],
  "lessThan": Decimal,
  "greaterThan": Decimal,
  "lessThanOrEqual": Decimal,
  "greaterThanOrEqual": Decimal
}
```

[Types](#group-Types)

## MaterialFilterSku

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "abc123",
  "greaterThan": "abc123",
  "lessThanOrEqual": "abc123",
  "greaterThanOrEqual": "xyz789",
  "like": "xyz789",
  "ilike": "xyz789"
}
```

[Types](#group-Types)

## MaterialFilterUnit

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "xyz789",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "abc123",
  "greaterThanOrEqual": "abc123"
}
```

[Types](#group-Types)

## MaterialSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |
| `NAME` |  |
| `SKU` |  |
| `UNIT` |  |
| `PRICE` |  |
| `MINIMUM_STOCK` |  |
| `MAXIMUM_STOCK` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## MaterialSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`MaterialSortField!`](#definition-MaterialSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## Movement

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

##### Example

```
{"id": 4}
```

[Types](#group-Types)

## MovementFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": false,
  "eq": 4,
  "notEq": 4,
  "in": [4],
  "lessThan": 4,
  "greaterThan": 4,
  "lessThanOrEqual": 4,
  "greaterThanOrEqual": "4"
}
```

[Types](#group-Types)

## MovementFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[MovementFilterInput!]`](#definition-MovementFilterInput) |  |
| `or` - [`[MovementFilterInput!]`](#definition-MovementFilterInput) |  |
| `not` - [`[MovementFilterInput!]`](#definition-MovementFilterInput) |  |
| `id` - [`MovementFilterId`](#definition-MovementFilterId) |  |

##### Example

```
{
  "and": [MovementFilterInput],
  "or": [MovementFilterInput],
  "not": [MovementFilterInput],
  "id": MovementFilterId
}
```

[Types](#group-Types)

## MovementSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## MovementSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`MovementSortField!`](#definition-MovementSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## MutationError

##### Description

An error generated by a failed mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `message` - [`String`](#definition-String) | The human readable error message |
| `shortMessage` - [`String`](#definition-String) | A shorter error message, with vars not replaced |
| `vars` - [`Json`](#definition-Json) | Replacements for the short message |
| `code` - [`String`](#definition-String) | An error code for the given error |
| `fields` - [`[String!]`](#definition-String) | The field or fields that produced the error |

##### Example

```
{
  "message": "abc123",
  "shortMessage": "abc123",
  "vars": Json,
  "code": "abc123",
  "fields": ["abc123"]
}
```

[Types](#group-Types)

## Order

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

##### Example

```
{"id": 4}
```

[Types](#group-Types)

## OrderCreateItemsInput

##### Fields

| Input Field | Description |
| --- | --- |
| `id` - [`ID`](#definition-ID) |  |
| `status` - [`String`](#definition-String) |  |
| `quantity` - [`Decimal`](#definition-Decimal) |  |
| `productId` - [`ID`](#definition-ID) |  |
| `laborCost` - [`Decimal`](#definition-Decimal) | Labor cost allocated to this order item during batch completion |
| `materialCost` - [`Decimal`](#definition-Decimal) | Material cost allocated to this order item during batch completion |
| `overheadCost` - [`Decimal`](#definition-Decimal) | Overhead cost allocated to this order item during batch completion |
| `unitCost` - [`Decimal`](#definition-Decimal) | Per-unit production cost captured at batch completion |
| `unitPrice` - [`Decimal`](#definition-Decimal) |  |
| `consumedAt` - [`DateTime`](#definition-DateTime) | Timestamp indicating materials were consumed for this item |

##### Example

```
{
  "id": 4,
  "status": "xyz789",
  "quantity": Decimal,
  "productId": "4",
  "laborCost": Decimal,
  "materialCost": Decimal,
  "overheadCost": Decimal,
  "unitCost": Decimal,
  "unitPrice": Decimal,
  "consumedAt": "2007-12-03T10:15:30Z"
}
```

[Types](#group-Types)

## OrderFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": true,
  "eq": "4",
  "notEq": "4",
  "in": [4],
  "lessThan": "4",
  "greaterThan": 4,
  "lessThanOrEqual": 4,
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## OrderFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[OrderFilterInput!]`](#definition-OrderFilterInput) |  |
| `or` - [`[OrderFilterInput!]`](#definition-OrderFilterInput) |  |
| `not` - [`[OrderFilterInput!]`](#definition-OrderFilterInput) |  |
| `id` - [`OrderFilterId`](#definition-OrderFilterId) |  |

##### Example

```
{
  "and": [OrderFilterInput],
  "or": [OrderFilterInput],
  "not": [OrderFilterInput],
  "id": OrderFilterId
}
```

[Types](#group-Types)

## OrderItem

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

##### Example

```
{"id": 4}
```

[Types](#group-Types)

## OrderItemFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": false,
  "eq": 4,
  "notEq": 4,
  "in": ["4"],
  "lessThan": 4,
  "greaterThan": "4",
  "lessThanOrEqual": "4",
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## OrderItemFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[OrderItemFilterInput!]`](#definition-OrderItemFilterInput) |  |
| `or` - [`[OrderItemFilterInput!]`](#definition-OrderItemFilterInput) |  |
| `not` - [`[OrderItemFilterInput!]`](#definition-OrderItemFilterInput) |  |
| `id` - [`OrderItemFilterId`](#definition-OrderItemFilterId) |  |

##### Example

```
{
  "and": [OrderItemFilterInput],
  "or": [OrderItemFilterInput],
  "not": [OrderItemFilterInput],
  "id": OrderItemFilterId
}
```

[Types](#group-Types)

## OrderItemSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## OrderItemSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`OrderItemSortField!`](#definition-OrderItemSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## OrderSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## OrderSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`OrderSortField!`](#definition-OrderSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## OrderUpdateItemsInput

##### Fields

| Input Field | Description |
| --- | --- |
| `id` - [`ID`](#definition-ID) |  |
| `status` - [`String`](#definition-String) |  |
| `quantity` - [`Decimal`](#definition-Decimal) |  |
| `productId` - [`ID`](#definition-ID) |  |
| `laborCost` - [`Decimal`](#definition-Decimal) | Labor cost allocated to this order item during batch completion |
| `materialCost` - [`Decimal`](#definition-Decimal) | Material cost allocated to this order item during batch completion |
| `overheadCost` - [`Decimal`](#definition-Decimal) | Overhead cost allocated to this order item during batch completion |
| `unitCost` - [`Decimal`](#definition-Decimal) | Per-unit production cost captured at batch completion |
| `unitPrice` - [`Decimal`](#definition-Decimal) |  |
| `consumedAt` - [`DateTime`](#definition-DateTime) | Timestamp indicating materials were consumed for this item |

##### Example

```
{
  "id": 4,
  "status": "xyz789",
  "quantity": Decimal,
  "productId": 4,
  "laborCost": Decimal,
  "materialCost": Decimal,
  "overheadCost": Decimal,
  "unitCost": Decimal,
  "unitPrice": Decimal,
  "consumedAt": "2007-12-03T10:15:30Z"
}
```

[Types](#group-Types)

## Product

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |
| `name` - [`String!`](#definition-String) |  |
| `status` - [`String!`](#definition-String) |  |
| `price` - [`Decimal!`](#definition-Decimal) |  |
| `photos` - [`[String!]`](#definition-String) | Array of photo URLs for the product |
| `featuredPhoto` - [`String`](#definition-String) | ID or reference to the featured photo from the photos array |
| `sellingAvailability` - [`String!`](#definition-String) | Customer-facing availability: available, preorder, or off |
| `maxDailyQuantity` - [`Int!`](#definition-Int) | Optional per-product capacity per day (0 = unlimited) |

##### Example

```
{
  "id": "4",
  "name": "xyz789",
  "status": "abc123",
  "price": Decimal,
  "photos": ["abc123"],
  "featuredPhoto": "abc123",
  "sellingAvailability": "xyz789",
  "maxDailyQuantity": 123
}
```

[Types](#group-Types)

## ProductFilterFeaturedPhoto

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["abc123"],
  "lessThan": "abc123",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "xyz789",
  "greaterThanOrEqual": "xyz789",
  "like": "abc123",
  "ilike": "abc123"
}
```

[Types](#group-Types)

## ProductFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": false,
  "eq": "4",
  "notEq": "4",
  "in": ["4"],
  "lessThan": "4",
  "greaterThan": 4,
  "lessThanOrEqual": 4,
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## ProductFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[ProductFilterInput!]`](#definition-ProductFilterInput) |  |
| `or` - [`[ProductFilterInput!]`](#definition-ProductFilterInput) |  |
| `not` - [`[ProductFilterInput!]`](#definition-ProductFilterInput) |  |
| `id` - [`ProductFilterId`](#definition-ProductFilterId) |  |
| `name` - [`ProductFilterName`](#definition-ProductFilterName) |  |
| `status` - [`ProductFilterStatus`](#definition-ProductFilterStatus) |  |
| `price` - [`ProductFilterPrice`](#definition-ProductFilterPrice) |  |
| `featuredPhoto` - [`ProductFilterFeaturedPhoto`](#definition-ProductFilterFeaturedPhoto) | ID or reference to the featured photo from the photos array |
| `sellingAvailability` - [`ProductFilterSellingAvailability`](#definition-ProductFilterSellingAvailability) | Customer-facing availability: available, preorder, or off |
| `maxDailyQuantity` - [`ProductFilterMaxDailyQuantity`](#definition-ProductFilterMaxDailyQuantity) | Optional per-product capacity per day (0 = unlimited) |

##### Example

```
{
  "and": [ProductFilterInput],
  "or": [ProductFilterInput],
  "not": [ProductFilterInput],
  "id": ProductFilterId,
  "name": ProductFilterName,
  "status": ProductFilterStatus,
  "price": ProductFilterPrice,
  "featuredPhoto": ProductFilterFeaturedPhoto,
  "sellingAvailability": ProductFilterSellingAvailability,
  "maxDailyQuantity": ProductFilterMaxDailyQuantity
}
```

[Types](#group-Types)

## ProductFilterMaxDailyQuantity

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`Int`](#definition-Int) |  |
| `notEq` - [`Int`](#definition-Int) |  |
| `in` - [`[Int!]`](#definition-Int) |  |
| `lessThan` - [`Int`](#definition-Int) |  |
| `greaterThan` - [`Int`](#definition-Int) |  |
| `lessThanOrEqual` - [`Int`](#definition-Int) |  |
| `greaterThanOrEqual` - [`Int`](#definition-Int) |  |

##### Example

```
{
  "isNil": true,
  "eq": 123,
  "notEq": 123,
  "in": [123],
  "lessThan": 987,
  "greaterThan": 987,
  "lessThanOrEqual": 987,
  "greaterThanOrEqual": 123
}
```

[Types](#group-Types)

## ProductFilterName

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |
| `like` - [`String`](#definition-String) |  |
| `ilike` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": true,
  "eq": "abc123",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "abc123",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "xyz789",
  "greaterThanOrEqual": "xyz789",
  "like": "abc123",
  "ilike": "abc123"
}
```

[Types](#group-Types)

## ProductFilterPrice

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`Decimal`](#definition-Decimal) |  |
| `notEq` - [`Decimal`](#definition-Decimal) |  |
| `in` - [`[Decimal!]`](#definition-Decimal) |  |
| `lessThan` - [`Decimal`](#definition-Decimal) |  |
| `greaterThan` - [`Decimal`](#definition-Decimal) |  |
| `lessThanOrEqual` - [`Decimal`](#definition-Decimal) |  |
| `greaterThanOrEqual` - [`Decimal`](#definition-Decimal) |  |

##### Example

```
{
  "isNil": true,
  "eq": Decimal,
  "notEq": Decimal,
  "in": [Decimal],
  "lessThan": Decimal,
  "greaterThan": Decimal,
  "lessThanOrEqual": Decimal,
  "greaterThanOrEqual": Decimal
}
```

[Types](#group-Types)

## ProductFilterSellingAvailability

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": true,
  "eq": "xyz789",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "xyz789",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "xyz789",
  "greaterThanOrEqual": "xyz789"
}
```

[Types](#group-Types)

## ProductFilterStatus

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`String`](#definition-String) |  |
| `notEq` - [`String`](#definition-String) |  |
| `in` - [`[String!]`](#definition-String) |  |
| `lessThan` - [`String`](#definition-String) |  |
| `greaterThan` - [`String`](#definition-String) |  |
| `lessThanOrEqual` - [`String`](#definition-String) |  |
| `greaterThanOrEqual` - [`String`](#definition-String) |  |

##### Example

```
{
  "isNil": false,
  "eq": "abc123",
  "notEq": "xyz789",
  "in": ["xyz789"],
  "lessThan": "xyz789",
  "greaterThan": "xyz789",
  "lessThanOrEqual": "abc123",
  "greaterThanOrEqual": "xyz789"
}
```

[Types](#group-Types)

## ProductSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |
| `NAME` |  |
| `STATUS` |  |
| `PRICE` |  |
| `FEATURED_PHOTO` |  |
| `SELLING_AVAILABILITY` |  |
| `MAX_DAILY_QUANTITY` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## ProductSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`ProductSortField!`](#definition-ProductSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## ProductionBatch

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

##### Example

```
{"id": "4"}
```

[Types](#group-Types)

## ProductionBatchFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": true,
  "eq": 4,
  "notEq": "4",
  "in": ["4"],
  "lessThan": "4",
  "greaterThan": 4,
  "lessThanOrEqual": 4,
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## ProductionBatchFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[ProductionBatchFilterInput!]`](#definition-ProductionBatchFilterInput) |  |
| `or` - [`[ProductionBatchFilterInput!]`](#definition-ProductionBatchFilterInput) |  |
| `not` - [`[ProductionBatchFilterInput!]`](#definition-ProductionBatchFilterInput) |  |
| `id` - [`ProductionBatchFilterId`](#definition-ProductionBatchFilterId) |  |

##### Example

```
{
  "and": [ProductionBatchFilterInput],
  "or": [ProductionBatchFilterInput],
  "not": [ProductionBatchFilterInput],
  "id": ProductionBatchFilterId
}
```

[Types](#group-Types)

## ProductionBatchSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## ProductionBatchSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`ProductionBatchSortField!`](#definition-ProductionBatchSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## PurchaseOrder

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

##### Example

```
{"id": "4"}
```

[Types](#group-Types)

## PurchaseOrderFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": true,
  "eq": 4,
  "notEq": "4",
  "in": [4],
  "lessThan": 4,
  "greaterThan": "4",
  "lessThanOrEqual": "4",
  "greaterThanOrEqual": 4
}
```

[Types](#group-Types)

## PurchaseOrderFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[PurchaseOrderFilterInput!]`](#definition-PurchaseOrderFilterInput) |  |
| `or` - [`[PurchaseOrderFilterInput!]`](#definition-PurchaseOrderFilterInput) |  |
| `not` - [`[PurchaseOrderFilterInput!]`](#definition-PurchaseOrderFilterInput) |  |
| `id` - [`PurchaseOrderFilterId`](#definition-PurchaseOrderFilterId) |  |

##### Example

```
{
  "and": [PurchaseOrderFilterInput],
  "or": [PurchaseOrderFilterInput],
  "not": [PurchaseOrderFilterInput],
  "id": PurchaseOrderFilterId
}
```

[Types](#group-Types)

## PurchaseOrderSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## PurchaseOrderSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`PurchaseOrderSortField!`](#definition-PurchaseOrderSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## SortOrder

##### Values

| Enum Value | Description |
| --- | --- |
| `DESC` |  |
| `DESC_NULLS_FIRST` |  |
| `DESC_NULLS_LAST` |  |
| `ASC` |  |
| `ASC_NULLS_FIRST` |  |
| `ASC_NULLS_LAST` |  |

##### Example

```
"DESC"
```

[Types](#group-Types)

## String

##### Description

The `String` scalar type represents textual data, represented as UTF-8 character sequences. The String type is most often used by GraphQL to represent free-form human-readable text.

##### Example

```
"xyz789"
```

[Types](#group-Types)

## Supplier

##### Fields

| Field Name | Description |
| --- | --- |
| `id` - [`ID!`](#definition-ID) |  |

##### Example

```
{"id": 4}
```

[Types](#group-Types)

## SupplierFilterId

##### Fields

| Input Field | Description |
| --- | --- |
| `isNil` - [`Boolean`](#definition-Boolean) |  |
| `eq` - [`ID`](#definition-ID) |  |
| `notEq` - [`ID`](#definition-ID) |  |
| `in` - [`[ID!]`](#definition-ID) |  |
| `lessThan` - [`ID`](#definition-ID) |  |
| `greaterThan` - [`ID`](#definition-ID) |  |
| `lessThanOrEqual` - [`ID`](#definition-ID) |  |
| `greaterThanOrEqual` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "isNil": false,
  "eq": 4,
  "notEq": "4",
  "in": ["4"],
  "lessThan": "4",
  "greaterThan": 4,
  "lessThanOrEqual": 4,
  "greaterThanOrEqual": "4"
}
```

[Types](#group-Types)

## SupplierFilterInput

##### Fields

| Input Field | Description |
| --- | --- |
| `and` - [`[SupplierFilterInput!]`](#definition-SupplierFilterInput) |  |
| `or` - [`[SupplierFilterInput!]`](#definition-SupplierFilterInput) |  |
| `not` - [`[SupplierFilterInput!]`](#definition-SupplierFilterInput) |  |
| `id` - [`SupplierFilterId`](#definition-SupplierFilterId) |  |

##### Example

```
{
  "and": [SupplierFilterInput],
  "or": [SupplierFilterInput],
  "not": [SupplierFilterInput],
  "id": SupplierFilterId
}
```

[Types](#group-Types)

## SupplierSortField

##### Values

| Enum Value | Description |
| --- | --- |
| `ID` |  |

##### Example

```
"ID"
```

[Types](#group-Types)

## SupplierSortInput

##### Fields

| Input Field | Description |
| --- | --- |
| `order` - [`SortOrder`](#definition-SortOrder) |  |
| `field` - [`SupplierSortField!`](#definition-SupplierSortField) |  |

##### Example

```
{"order": "DESC", "field": "ID"}
```

[Types](#group-Types)

## UpdateCustomerInput

##### Fields

| Input Field | Description |
| --- | --- |
| `type` - [`String`](#definition-String) |  |
| `firstName` - [`String`](#definition-String) |  |
| `lastName` - [`String`](#definition-String) |  |
| `email` - [`String`](#definition-String) |  |
| `phone` - [`String`](#definition-String) |  |
| `billingAddress` - [`JsonString`](#definition-JsonString) |  |
| `shippingAddress` - [`JsonString`](#definition-JsonString) |  |

##### Example

```
{
  "type": "xyz789",
  "firstName": "xyz789",
  "lastName": "xyz789",
  "email": "abc123",
  "phone": "xyz789",
  "billingAddress": JsonString,
  "shippingAddress": JsonString
}
```

[Types](#group-Types)

## UpdateCustomerResult

##### Description

The result of the :update\_customer mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Customer`](#definition-Customer) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Customer,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## UpdateMaterialInput

##### Fields

| Input Field | Description |
| --- | --- |
| `name` - [`String`](#definition-String) |  |
| `sku` - [`String`](#definition-String) |  |
| `unit` - [`String`](#definition-String) |  |
| `price` - [`Decimal`](#definition-Decimal) |  |
| `minimumStock` - [`Decimal`](#definition-Decimal) |  |
| `maximumStock` - [`Decimal`](#definition-Decimal) |  |

##### Example

```
{
  "name": "abc123",
  "sku": "xyz789",
  "unit": "abc123",
  "price": Decimal,
  "minimumStock": Decimal,
  "maximumStock": Decimal
}
```

[Types](#group-Types)

## UpdateMaterialResult

##### Description

The result of the :update\_material mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Material`](#definition-Material) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Material,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## UpdateOrderInput

##### Fields

| Input Field | Description |
| --- | --- |
| `deliveryDate` - [`DateTime`](#definition-DateTime) |  |
| `invoiceNumber` - [`String`](#definition-String) |  |
| `invoiceStatus` - [`String`](#definition-String) |  |
| `invoicedAt` - [`DateTime`](#definition-DateTime) |  |
| `paymentMethod` - [`String`](#definition-String) |  |
| `discountType` - [`String`](#definition-String) |  |
| `discountValue` - [`Decimal`](#definition-Decimal) |  |
| `deliveryMethod` - [`String`](#definition-String) |  |
| `status` - [`String`](#definition-String) |  |
| `taxTotal` - [`Decimal`](#definition-Decimal) |  |
| `shippingTotal` - [`Decimal`](#definition-Decimal) |  |
| `discountTotal` - [`Decimal`](#definition-Decimal) |  |
| `customerId` - [`ID`](#definition-ID) |  |
| `items` - [`[OrderUpdateItemsInput!]`](#definition-OrderUpdateItemsInput) |  |

##### Example

```
{
  "deliveryDate": "2007-12-03T10:15:30Z",
  "invoiceNumber": "abc123",
  "invoiceStatus": "xyz789",
  "invoicedAt": "2007-12-03T10:15:30Z",
  "paymentMethod": "xyz789",
  "discountType": "xyz789",
  "discountValue": Decimal,
  "deliveryMethod": "abc123",
  "status": "abc123",
  "taxTotal": Decimal,
  "shippingTotal": Decimal,
  "discountTotal": Decimal,
  "customerId": 4,
  "items": [OrderUpdateItemsInput]
}
```

[Types](#group-Types)

## UpdateOrderItemInput

##### Fields

| Input Field | Description |
| --- | --- |
| `quantity` - [`Decimal`](#definition-Decimal) |  |
| `status` - [`String`](#definition-String) |  |
| `consumedAt` - [`DateTime`](#definition-DateTime) | Timestamp indicating materials were consumed for this item |
| `materialCost` - [`Decimal`](#definition-Decimal) | Material cost allocated to this order item during batch completion |
| `laborCost` - [`Decimal`](#definition-Decimal) | Labor cost allocated to this order item during batch completion |
| `overheadCost` - [`Decimal`](#definition-Decimal) | Overhead cost allocated to this order item during batch completion |
| `unitCost` - [`Decimal`](#definition-Decimal) | Per-unit production cost captured at batch completion |

##### Example

```
{
  "quantity": Decimal,
  "status": "xyz789",
  "consumedAt": "2007-12-03T10:15:30Z",
  "materialCost": Decimal,
  "laborCost": Decimal,
  "overheadCost": Decimal,
  "unitCost": Decimal
}
```

[Types](#group-Types)

## UpdateOrderItemResult

##### Description

The result of the :update\_order\_item mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`OrderItem`](#definition-OrderItem) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": OrderItem,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## UpdateOrderResult

##### Description

The result of the :update\_order mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Order`](#definition-Order) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Order,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## UpdateProductInput

##### Fields

| Input Field | Description |
| --- | --- |
| `name` - [`String`](#definition-String) |  |
| `status` - [`String`](#definition-String) |  |
| `price` - [`Decimal`](#definition-Decimal) |  |
| `sku` - [`String`](#definition-String) |  |
| `photos` - [`[String!]`](#definition-String) | Array of photo URLs for the product |
| `featuredPhoto` - [`String`](#definition-String) | ID or reference to the featured photo from the photos array |
| `sellingAvailability` - [`String`](#definition-String) | Customer-facing availability: available, preorder, or off |
| `maxDailyQuantity` - [`Int`](#definition-Int) | Optional per-product capacity per day (0 = unlimited) |

##### Example

```
{
  "name": "abc123",
  "status": "abc123",
  "price": Decimal,
  "sku": "abc123",
  "photos": ["abc123"],
  "featuredPhoto": "xyz789",
  "sellingAvailability": "xyz789",
  "maxDailyQuantity": 123
}
```

[Types](#group-Types)

## UpdateProductResult

##### Description

The result of the :update\_product mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Product`](#definition-Product) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Product,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## UpdatePurchaseOrderInput

##### Fields

| Input Field | Description |
| --- | --- |
| `status` - [`String`](#definition-String) |  |
| `orderedAt` - [`DateTime`](#definition-DateTime) |  |
| `receivedAt` - [`DateTime`](#definition-DateTime) |  |
| `supplierId` - [`ID`](#definition-ID) |  |

##### Example

```
{
  "status": "abc123",
  "orderedAt": "2007-12-03T10:15:30Z",
  "receivedAt": "2007-12-03T10:15:30Z",
  "supplierId": "4"
}
```

[Types](#group-Types)

## UpdatePurchaseOrderResult

##### Description

The result of the :update\_purchase\_order mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`PurchaseOrder`](#definition-PurchaseOrder) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": PurchaseOrder,
  "errors": [MutationError]
}
```

[Types](#group-Types)

## UpdateSupplierInput

##### Fields

| Input Field | Description |
| --- | --- |
| `name` - [`String`](#definition-String) |  |
| `contactName` - [`String`](#definition-String) |  |
| `contactEmail` - [`String`](#definition-String) |  |
| `contactPhone` - [`String`](#definition-String) |  |
| `notes` - [`String`](#definition-String) |  |

##### Example

```
{
  "name": "xyz789",
  "contactName": "xyz789",
  "contactEmail": "abc123",
  "contactPhone": "abc123",
  "notes": "xyz789"
}
```

[Types](#group-Types)

## UpdateSupplierResult

##### Description

The result of the :update\_supplier mutation

##### Fields

| Field Name | Description |
| --- | --- |
| `result` - [`Supplier`](#definition-Supplier) | The successful result of the mutation |
| `errors` - [`[MutationError!]!`](#definition-MutationError) | Any errors generated, if the mutation failed |

##### Example

```
{
  "result": Supplier,
  "errors": [MutationError]
}
```

[Documentation by Anvil SpectaQL](https://github.com/anvilco/spectaql)