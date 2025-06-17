```mermaid
graph LR
    Item_Master_Data_Management["Item Master Data Management"]
    Inventory_Control_Movement["Inventory Control & Movement"]
    Serial_Batch_Tracking["Serial & Batch Tracking"]
    Quality_Control["Quality Control"]
    Manufacturing_Core["Manufacturing Core"]
    Production_Planning["Production Planning"]
    Job_Card_Management["Job Card Management"]
    Landed_Cost_Management["Landed Cost Management"]
    Inventory_Valuation["Inventory Valuation"]
    Shipping_Packing["Shipping & Packing"]
    Item_Master_Data_Management -- "Provides item definitions and attributes to" --> Inventory_Control_Movement
    Item_Master_Data_Management -- "Provides Bill of Material (BOM) and item details to" --> Manufacturing_Core
    Item_Master_Data_Management -- "Provides item data for planning to" --> Production_Planning
    Item_Master_Data_Management -- "Provides item details for cost allocation to" --> Landed_Cost_Management
    Item_Master_Data_Management -- "Provides item data for valuation to" --> Inventory_Valuation
    Item_Master_Data_Management -- "Provides item details for packing to" --> Shipping_Packing
    Item_Master_Data_Management -- "Provides item details for tracking to" --> Serial_Batch_Tracking
    Item_Master_Data_Management -- "Provides item details for inspection to" --> Quality_Control
    Item_Master_Data_Management -- "Provides item details for operations to" --> Job_Card_Management
    Inventory_Control_Movement -- "Relies on" --> Item_Master_Data_Management
    Inventory_Control_Movement -- "Utilizes" --> Serial_Batch_Tracking
    Inventory_Control_Movement -- "Triggers and receives results from" --> Quality_Control
    Inventory_Control_Movement -- "Provides raw materials to and receives finished goods from it" --> Manufacturing_Core
    Inventory_Control_Movement -- "Receives material requests from and provides current stock levels" --> Production_Planning
    Inventory_Control_Movement -- "Receives cost adjustments from" --> Landed_Cost_Management
    Inventory_Control_Movement -- "Provides stock movement data to" --> Inventory_Valuation
    Inventory_Control_Movement -- "Provides items for dispatch to" --> Shipping_Packing
    Shipping_Packing -- "Updates stock status in" --> Inventory_Control_Movement
    Serial_Batch_Tracking -- "Provides detailed serial/batch information for stock movements to" --> Inventory_Control_Movement
    Serial_Batch_Tracking -- "Provides traceability for quality inspections to" --> Quality_Control
    Quality_Control -- "Receives item details from" --> Item_Master_Data_Management
    Quality_Control -- "Records inspection results against specific serial/batch numbers from" --> Serial_Batch_Tracking
    Quality_Control -- "Provides inspection results to" --> Inventory_Control_Movement
    Manufacturing_Core -- "Uses BOM and item details from" --> Item_Master_Data_Management
    Manufacturing_Core -- "Consumes materials from and produces finished goods into" --> Inventory_Control_Movement
    Manufacturing_Core -- "Receives work orders from and provides production status" --> Production_Planning
    Manufacturing_Core -- "Creates job cards for" --> Job_Card_Management
    Job_Card_Management -- "Provides progress updates to" --> Manufacturing_Core
    Production_Planning -- "Uses item master data from" --> Item_Master_Data_Management
    Production_Planning -- "Generates material requests based on inventory levels from" --> Inventory_Control_Movement
    Production_Planning -- "Generates work orders for" --> Manufacturing_Core
    Landed_Cost_Management -- "Receives item and purchase receipt data from" --> Inventory_Control_Movement
    Landed_Cost_Management -- "Sends cost adjustments to" --> Inventory_Control_Movement
    Inventory_Valuation -- "Receives stock movement data from" --> Inventory_Control_Movement
    Inventory_Valuation -- "Uses item master data from" --> Item_Master_Data_Management
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Item Master Data Management
This foundational component manages all static and descriptive information about items. This includes defining item attributes, managing barcodes, setting up pricing rules, and configuring reorder levels. It serves as the single source of truth for all item-related data across the ERP system.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/item/item.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.item.item` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/item_attribute/item_attribute.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.item_attribute.item_attribute` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/item_price/item_price.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.item_price.item_price` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/price_list/price_list.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.price_list.price_list` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/item_reorder/item_reorder.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.item_reorder.item_reorder` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/get_item_details.py#L58-L156" target="_blank" rel="noopener noreferrer">`erpnext.stock.get_item_details` (58:156)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/item_barcode/item_barcode.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.item_barcode.item_barcode` (0:0)</a>


### Inventory Control & Movement
This core component is responsible for tracking real-time stock levels and managing all physical movements of goods. This includes recording stock receipts (e.g., from purchases or production), issues (e.g., for sales or consumption), internal transfers between warehouses, and adjustments for discrepancies. It relies heavily on the StockController (within erpnext.controllers.stock_controller) to validate and process these movements and generate corresponding ledger entries.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/stock_entry/stock_entry.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.stock_entry.stock_entry` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/warehouse/warehouse.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.warehouse.warehouse` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/bin/bin.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.bin.bin` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/delivery_note/delivery_note.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.delivery_note.delivery_note` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/purchase_receipt/purchase_receipt.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.purchase_receipt.purchase_receipt` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/stock_reconciliation/stock_reconciliation.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.stock_reconciliation.stock_reconciliation` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/stock_balance.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.stock_balance` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/stock_ledger.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.stock_ledger` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/stock_ledger_entry/stock_ledger_entry.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.stock_ledger_entry.stock_ledger_entry` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/stock_entry_detail/stock_entry_detail.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.stock_entry_detail.stock_entry_detail` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/putaway_rule/putaway_rule.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.putaway_rule.putaway_rule` (0:0)</a>


### Serial & Batch Tracking
This component provides granular control over inventory by managing unique serial numbers for individual items and batch numbers for groups of items. It enables traceability, warranty tracking, and expiry date management, which are vital for industries with strict regulatory requirements or perishable goods.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/serial_no/serial_no.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.serial_no.serial_no` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/batch/batch.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.batch.batch` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/serial_and_batch_bundle/serial_and_batch_bundle.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.serial_and_batch_bundle.serial_and_batch_bundle` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/serial_batch_bundle.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.serial_batch_bundle` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/serial_and_batch_entry/serial_and_batch_entry.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.serial_and_batch_entry.serial_and_batch_entry` (0:0)</a>


### Quality Control
This component integrates quality assurance into inventory and manufacturing processes. It allows for the definition of quality inspection templates and parameters, facilitating inspections at various stages (e.g., incoming materials, in-process, final product) to ensure goods meet specified quality standards.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/quality_inspection/quality_inspection.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.quality_inspection.quality_inspection` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/quality_inspection_template/quality_inspection_template.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.quality_inspection_template.quality_inspection_template` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/quality_inspection_parameter/quality_inspection_parameter.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.quality_inspection_parameter.quality_inspection_parameter` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/quality_inspection_parameter_group/quality_inspection_parameter_group.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.quality_inspection_parameter_group.quality_inspection_parameter_group` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/quality_inspection_reading/quality_inspection_reading.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.quality_inspection_reading.quality_inspection_reading` (0:0)</a>


### Manufacturing Core
This is the heart of the manufacturing operations. It defines how products are assembled or produced through Bills of Material (BOMs), which list the raw materials and operations required. Work Orders then translate these BOMs into actionable production tasks, tracking material consumption and finished goods production.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/manufacturing/doctype/bom/bom.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.manufacturing.doctype.bom.bom` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/manufacturing/doctype/work_order/work_order.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.manufacturing.doctype.work_order.work_order` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/manufacturing/doctype/operation/operation.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.manufacturing.doctype.operation.operation` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/manufacturing/doctype/routing/routing.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.manufacturing.doctype.routing.routing` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/manufacturing/doctype/workstation/workstation.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.manufacturing.doctype.workstation.workstation` (0:0)</a>


### Production Planning
This component focuses on optimizing manufacturing schedules and resource allocation. It generates material requests based on sales orders or projected demand and creates detailed production plans to ensure that manufacturing processes are aligned with business needs and inventory availability.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/manufacturing/doctype/production_plan/production_plan.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.manufacturing.doctype.production_plan.production_plan` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/material_request/material_request.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.material_request.material_request` (0:0)</a>


### Job Card Management
This component breaks down work orders into smaller, trackable job cards, representing individual operations or tasks. It allows for detailed tracking of time spent, resources consumed, and progress at each workstation, providing granular control and visibility into the production floor.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/manufacturing/doctype/job_card/job_card.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.manufacturing.doctype.job_card.job_card` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/manufacturing/doctype/downtime_entry/downtime_entry.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.manufacturing.doctype.downtime_entry.downtime_entry` (0:0)</a>


### Landed Cost Management
This component is crucial for accurately determining the true cost of purchased items. It allows for the allocation of additional costs, such as freight, customs duties, and insurance, to the cost of goods, which directly impacts inventory valuation and profitability analysis.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/landed_cost_voucher/landed_cost_voucher.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.landed_cost_voucher.landed_cost_voucher` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/landed_cost_item/landed_cost_item.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.landed_cost_item.landed_cost_item` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/landed_cost_purchase_receipt/landed_cost_purchase_receipt.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.landed_cost_purchase_receipt.landed_cost_purchase_receipt` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/landed_cost_taxes_and_charges/landed_cost_taxes_and_charges.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.landed_cost_taxes_and_charges.landed_cost_taxes_and_charges` (0:0)</a>


### Inventory Valuation
This component defines and applies various accounting methods (e.g., FIFO, LIFO, Weighted Average) for valuing inventory. It also handles the reposting of item valuations, ensuring that the financial value of inventory accurately reflects the chosen accounting principles.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/valuation.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.valuation` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/repost_item_valuation/repost_item_valuation.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.repost_item_valuation.repost_item_valuation` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/stock_ledger_entry/stock_ledger_entry.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.stock_ledger_entry.stock_ledger_entry` (0:0)</a>


### Shipping & Packing
This component manages the final stages of outbound logistics. It facilitates the creation of packing slips, organizes items into parcels, and manages delivery trips, ensuring that goods are correctly prepared and dispatched to customers or other destinations.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/packing_slip/packing_slip.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.packing_slip.packing_slip` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/shipment/shipment.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.shipment.shipment` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/delivery_trip/delivery_trip.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.delivery_trip.delivery_trip` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/packed_item/packed_item.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.packed_item.packed_item` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/delivery_note/delivery_note.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.delivery_note.delivery_note` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/shipment_parcel/shipment_parcel.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.shipment_parcel.shipment_parcel` (0:0)</a>
- <a href="https://github.com/frappe/erpnext/blob/master/erpnext/stock/doctype/pick_list/pick_list.py#L0-L0" target="_blank" rel="noopener noreferrer">`erpnext.stock.doctype.pick_list.pick_list` (0:0)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)