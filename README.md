# Car Sales Agreement

The purpose of this DAML project is to implement a simple car sales agreement system. There are several templates that help create and manage seller-buyer sales agreements.

# Data Records

CarDetails

CarDetails represents the details about a car, such as its model, license plate number, color, and production year.

SalesDetails

SalesDetails data types represent the details of a car sale, including the sale amount, currency, sale date, and the car's details.

# templates

SalesAgreement Template

This template represents a sales agreement contract between a seller and a buyer. Seller and buyer signatory roles are enforced, as well as the parties involved.

SalesProposal Template

A SalesProposal template is used to propose a sales agreement. It includes the seller, buyer, and sales details. Proposals can be accepted or rejected by the buyer, and sellers can regret it.

SalesRejection Template

SalesRejection represents the rejection of a sales proposal. It includes the seller, buyer, and reason for rejection. It is also possible for the seller to change the sales details and create a new sales proposal.

##

By creating a SalesProposal contract with the relevant details, the seller initiates a sales proposal.

By selecting AcceptSalesProposal or RejectSalesProposal, the buyer can accept or reject the proposal.

During the RejectSalesProposal choice, the buyer provides a reason for rejecting the proposal.

When the buyer accepts the proposal, a SalesAgreement contract is created.

Sellers can regret proposals using the RegretProposal choice.

### II. Workflow

1. Obtain the parties involved (seller and buyer) by calling the setupParties script.

2. Define the details of the car to be sold, including the model, license plate number, color, and production year.

3. Define the sales details, including the amount, currency, sale date, and the car's data from the CarDetails type.

4. Submit a sales proposal from the seller to the buyer using the createCmd SalesProposal.

5. The buyer rejects the sales proposal by exercising the RejectSalesProposal choice on the sales proposal contract. A reason for the rejection is provided.

6. The seller modifies the sales details by creating a new sales proposal using the ChangeDetails choice on the sales rejection contract. The modified sales details are passed as arguments.

7. The buyer accepts the modified sales proposal by exercising the AcceptSalesProposal choice on the new sales proposal contract.

At this point, a sales agreement contract is created, representing the finalized sales agreement between the seller and the buyer.

### Building

To compile the project

```

$ daml build

```

### Testing

To test all scripts:

Either run the pre-written script in the `Test.daml` under /daml OR run:

```

$ daml test

```

### Running

To load the project into the sandbox and start navigator:

```

$ daml start

```

