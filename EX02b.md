# **Normalization of Veterinary List**

## Step 1
The given list displays all 8 qualities of a relation, so we may proceed to subsequent steps.

## Step 2
Candidate keys must be identified, and are as follows:

• PetName

• OwnerLastName, OwnerPhone

• PetDOB

• Date

• PetID - Surrogate

• Invoice# - Surrogate

## Step 3
We can now determine all of the functional dependencies; these are the candidate keys that can describe all other column values. These functional dependencies (without the surrogate keys) are written accordingly:

• PetName → (PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Charge)

• OwnerLastName, → (PetName, PetType, PetBreed, PetDOB, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Charge)

• Service → (PetName, PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Charge)

## Step 4
We can see that some determinants are not candidate keys; Service and owners name by itself. This tells us that there are normalization issues with this list. We can either create a new list with the functional dependency being the relation between the distinct tables (i.e. foreign key) or create a new table with a surrogate key and a foreign key to relate the tables.
We chose to do both. We created three themes out of the original list; Pet Info, Owner Info, and Invoices. We created 2 surrogate keys; PetID and Invoice#. These became the primary keys in Pet info (PetID) and Invoices (Invoice#) respectively. The notation for the 3 tables is written as follows with Surrogate keys bolded and foreign keys italicized with the primary keys listed first in the parentheses.

• Pet Info (**Pet ID**, *OwnerLastName*, PetBreed, PetType, PetName,PetDOB)

• Owner Info (*OwnerLastName*, Owner Phone, OwnersFirstName, OwnerEmail

• Invoices (**Invoice#**, PetID, Service, Date, charge, *OwnerLastName*)
