## Synopsis

This project contains a demo OIC Process solution that receives a sales Order and posts it to SCM cloud after reviews.

For more information about this project, refer to the blog at:
http://www.ateam-oracle.com/saas-workflow-extensions-using-process-cloud-service/

## Code Example

Project contains OIC Process code sample with embedded SCM WSDLs from release 13 of Oracle Fusion Supply Chain Management (SCM)

- SalesOrderProcess.zip : This file contains a OIC process cloud export file (exp)  ready to be imported into the PCS Instance.

## Motivation

Customers look for ways to pre-process orders going into SCM cloud and also look for ways to improve manual review processes using cloud solutions. 

## Installation

To run the project, SCM cloud and OIC instances are required. 
1. Import the .exp file into OIC Process instance. 
2. Once the project is imported, validate and fix any issues reported.
3. Deploy the project to a test instance. 
4. Update the SCM cloud connection/credentials information with the working SCM cloud instance.
5. Make sure to assign users to the process roles defined by the project. 

## API Reference
This sample uses ReceiveOrderRequestService of SCM cloud's order management application.  WSDL for the service is accessible at:

```
https://{SCM cloud host}:{port}/soa-infra/services/default/DooDecompReceiveOrderExternalComposite/ReceiveOrderRequestService?wsdl  
```

## Tests

Once the OIC Process project is imported and updated with SCM cloud connectivity information, deploy it to a test instance.

To test the project:
1. Launch a new instance of the SalesOrderProcess. This can be done through Process admin UI or via OIC Process API.
2. A human task is sent to the inbox of process administrator. 
3. Open the task and fill-in the order information.
4. Click submit. Order is sent to reviewer. 
5. Reviewer can update order and send for final approval.
6. Approver can approve or reject the order.
7. If approved, the order is sent to SCM cloud.
8. If rejected, the order is sent back to reviewer for update, along with notes. 

## Contributors

Mani Krishnan

