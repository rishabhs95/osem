# Implementing Ticket Payment Feature
The project focuses on making the ticket payment procedure smoother and thereby the User Experience better.

## Implementation Plan
- Proper documentation and tests for all deliverables
  - Documentation will be written first describing project's structure 
  - Code will be written following TDD workflow.
- Define payment state machine transitions
  - The state machine will work like a Deterministic Finite State Automaton and will prevent the system going into an inconsistent state.
- Integrate Stripe payment gateway for ticket payments
  - Develop an API for consuming Stripe gateway with ActiveMerchant gem.
- Appropriate notifications updates for payments
  - Develop script for sending notifications to users for each payment with its details
- Persist user payment preferences
  - if required, store encrypterd user payment preference information.
- Update admin views to check payment status
  - update the admininstator's conference management page for ticket payment summaries for all their subscribers.

### Testing
The main focus of this project will be producing a well tested and secure code following the Test-driven Development methodology.

### State Machine
The transitions will follow a path like:
  - NOT PAID -> IN PROGRESS -> CANCELLED/DECLINED/SUCCESSFUL
  - CANCELLED/DECLINED -> NOT PAID
  - SUCCESSFUL -> PAID

### Consume ActiveMerchant gem with Stripe billing gateway
 - We will integrate the Stripe payment gateway to our application using ActiveMerchant gem which helps in making a modularized code and helps in moving the payment gateway code away from the payment code logic.
   - This means that we can easily change our payment gateway in future if needed without affecting the code and making the overall process smoother and easier.

 - Another options is to integrate Stripe payment gateway directly to our application through Javascript,whicb will be more secure but it will reduce our code modularity and changing payment gateway in future won't be that easy.

### Payment Status notifications
we will provide the concerned parties(i.e., user making the payments and administrators managing the conference) with appropriate notifications.
for this we may look out for these options:
  - notifications provided by Stripe payment gateway
  - develop a mailbot for delivering these notifications

### Persist User payment preferences
may generate security related issues for storing encrypted payment related user's information

### Update admin views
Conference administrator must recieve information related to the tickets sold and corresponding payments recieved.
Administrator views at http://localhost:3000/admin/conference/{conference_name}/tickets should show this summarised information.
