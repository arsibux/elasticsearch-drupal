# Commerce Product { Custom Developement }

- UAPI Validation
		- Get device selling price
				- Param { field_uapi } Device Code
				- Returning Large data over 12000 lines json data 
					- Cash list Count
					- Installment Count
					- Subsidies Count
					- with proper status code of api.
		- Get variations of product with given device code.
			- Add voilations for validations
 	
- Add and Edit Action
   - Adding custom handle { device_product_custom_submit }. Creating two queues.
   - Create queue item { device_prod_var_extra_fields_save_queue }.
   - Process queue item
     - Getting device product variation for { Device UAPI } from DRUPAL CMS
   	 - Getting device selling price from { UAPI  SYSTEM }.
   	 - Checking list of installment available from device UAPI.
   	 - Updating the device Product Variation Entity
   	 - Update device product Accessory.{ saving the product. }
	   - Create queue item { device_details_save_queue } queue.
	   - Process queue item
	     - Getting device product variation for {Device UAPI} from DRUPAL CMS.
	     - Update product variation stock.	     	
	     	- Unpublish product variation stock entity { uapi }
	     		- Getting all product variation stock entities with { status=1 } and make all { status=0 } DRUPAL CMS 	     	
	     	- Unpublish device plan committment { uapi }
	     		- Getting all device plan commitment entities with { status=1 } and make all { status=0 } DRUPAL CMS	     	
	     	- Get device selling price { UAPI  SYSTEM }.
	     	- Save device list cash
	     		- Iteration cash list data and get device list cash entity.
	     			- update else create new device list entity.	     
	     	- Save device plan installments with 0
	     		- Iteration plan installments and get device plan installment entity.
     				- update else create new device plan installment entity.
	     	- Save device plan installments with =1
	     		- Repeate of above.