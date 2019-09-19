# **Normalization of Veterinarian List**

## Step 1
The table upholds all 8 qualities of a relation, so we will continue to Step 2.

## Step 2
Candidate keys must be identified, which are keys that can be used to uniquely identify each row in a relation. The candidate keys are found below:

• PetName

• OwnerLastName 

• OwnerPhone

• PetDOB

• Date

• PetID - Surrogate Key

• InvoiceNumber - Surrogate Key

## Step 3
Now we must determine all of the functional dependencies; these are the candidate keys that can describe all other column values. These functional dependencies, excluding the surrogate keys, are found below:

• PetName → (PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Charge)

• OwnerLastName, → (PetName, PetType, PetBreed, PetDOB, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Charge)

• Service → (PetName, PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Charge)

## Step 4
We now see some determinants are not candidate keys; Service and OwnerLastName. This means the relation is not normalized as is. We have chosen to create a new table with a surrogate key and a foreign key to relate the tables, as well as connect a new relation to the original with a foreign key. We created three themes out of the original list; Pet Info, Owner Info, and Invoices. We created 2 surrogate keys; PetID and InvoiceNumber. These became the primary keys in Pet Info (PetID) and Invoices (InvoiceNumber) respectively. The notation for the 3 tables is found below with surrogate keys bolded and foreign keys italicized with the primary keys listed first in the parentheses.

• Pet Info (**PetID**, *OwnerLastName*, PetBreed, PetType, PetName,PetDOB)

• Owner Info (*OwnerLastName*, Owner Phone, OwnersFirstName, OwnerEmail)

• Invoices (**InvoiceNumber**, PetID, Service, Date, charge, *OwnerLastName*)
