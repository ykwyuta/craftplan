# Open-source ERP for artisanal manufacturers

From raw materials to finished products, Craftplan brings all essential
business tools into one platform. Manage your catalog, inventory, orders,
and production process without paying for multiple separate platforms.

[Get Started](/craftplan/docs/self-hosting/) [Live Demo](https://craftplan.fly.dev) [View on GitHub](https://github.com/puemos/craftplan)

Log in with `test@test.com` / `Aa123123123123`

![Craftplan production planner showing schedule, make sheet, and completion snapshot](/craftplan/screenshots/plan.webp)

Production planner with schedule, make sheet, and cost snapshots

## Everything you need to run your workshop

### Catalog & BOMs

Manage products with versioned Bills of Materials, labor steps, cost rollups, and pricing guidance.

### Inventory Control

Track raw materials, lots, stock movements, allergens, nutritional facts, and forecasted demand.

### Order Management

Process customer orders with status tracking, calendar view, delivery scheduling, and invoicing.

### Production Planning

Weekly planner with schedule, make sheet, and materials tabs. Print-ready production runs.

### Production Batching

Batch workflow from allocation through consumption to completion with cost snapshots.

### Purchasing

Manage suppliers and purchase orders. Receive POs directly into inventory stock.

### CRM

Customer database with addresses, order history, and per-customer statistics.

## Built with

Elixir  Ash Framework  Phoenix LiveView  PostgreSQL  Tailwind CSS

## Get up and running

1. 1

   Clone & configure

   `git clone ... && cd craftplan && cp .env.example .env`
2. 2

   Generate secrets

   `openssl rand -base64 48`
3. 3

   Start everything

   `docker compose up -d`
4. 4

   Open the app

   `Visit localhost:4000`

See the [self-hosting guide](/craftplan/docs/self-hosting/) for detailed instructions.