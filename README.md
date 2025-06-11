[Link to the Requirements section](#Requirements)

# Technologies
- Authorization/Authentication: NextAuth
- Frontend/Backend: NextJS
- Database: MongoDB
- Image storage: Deployed with website on Vercel
- Web host: Vercel
- Data sync: Power automate for name re-linking

# Terminology
- Borrower:
    - Anyone who can borrow gear, can be staff, student or admin
- Approved lending staff:
    - Lending staff are approved conditionally by admins

# Requirements
This section of the document relates to the needs of the application and how they should work
- Inventory of items with the following fields:
    - TODO
- Gear catalogue for people to browse

# Asset categories
- Consumables
    - Items that diminish without being returned
- Extras
    - Items that are returned but don't have unique identifiers
- Equipment
    - Items that have unique identifiers and associated QR codes

# Authorization
- Types of users:
    - Admin (Mitch and I)
        - Access to admin tools
        - Create, read, update and delete users
        - Create, read, update and delete gear
        - Assign gear to Borrowers and approve requests
        - HY login details
    - Approved Lending Staff (ALS) (Approved by Mitch and I to borrow and lend gear)
        - Create, read, update and delete gear
        - Assign gear to Borrowers and approve requests
        - HY login details
    - Borrowers (Students and Staff)
        - No login required
        - Can make a booking request
        - Need to remember their own unique identifier

# Access Areas
- Gear catalogue (Requires borrower or higher authorization)
- Admin area (Requires Approved Lending staff or higher authorization)

# Workflows
## Borrowing
### Borrower created booking requests
1. Borrower logs in with simple USER
2. Browse gear and add to cart
3. Create booking request - Can check status of booking request on /requests page
4. Lending staff will either [APPROVE, APPROVE WITH CHANGE or DENY]
5. Borrower, Lending staff and Admin will receive email containing details of booking, timeline, gear and notes

### ALS or higher created booking requests
1. User logs in to admin tool panel
2. User assigns gear to Borrower and approves

## Checkout
### ALS or higher on the day checkout
1. User assigns specific items to Borrower
2. Manually choose or scan gear to be associated with booking