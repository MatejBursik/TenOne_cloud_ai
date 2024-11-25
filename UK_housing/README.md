# UK Housing

## Working order for data cleaning
1) initial_cleaning.ipynb
2) outliers.ipynb
3) date_of_transfer.ipynb

## Data source
[Link](https://www.kaggle.com/datasets/hm-land-registry/uk-housing-prices-paid/data)
Due to the size of the file being 2.24 GB, I decided to gitignore the file

## Data information from the source

### Transaction unique identifier
A reference number which is generated automatically when recording each published sale. The number is unique and will change each time a sale is recorded.

### Price
Sale price stated on the transfer deed.

### Date of Transfer
Date when the sale was completed, as stated on the transfer deed.

### Property Type
- D = Detached
- S = Semi-Detached
- T = Terraced
- F = Flats/Maisonettes
- O = Other

Note:
we only record the above categories to describe property type, we do not separately identify bungalows.
end-of-terrace properties are included in the Terraced category above.
‘Other’ is only valid where the transaction relates to a property type that is not covered by existing values.

### Old/New
Indicates the age of the property and applies to all price paid transactions, residential and non-residential.
- Y = a newly built property
- N = an established residential building

### Duration
Relates to the tenure:
- F = Freehold
- L = Leasehold
- etc. (U...)

Note:
HM Land Registry does not record leases of 7 years or less in the Price Paid Dataset.

### Town/City, District, County
3 individual columns that provide location of the property.

### PPD Category Type
Indicates the type of Price Paid transaction.
- A = Standard Price Paid entry, includes single residential property sold for full market value.
- B = Additional Price Paid entry including transfers under a power of sale/repossessions, buy-to-lets (where they can be identified by a Mortgage) and transfers to non-private individuals. Note that category B does not separately identify the transaction types stated.

HM Land Registry has been collecting information on Category A transactions from January 1995. Category B transactions were identified from October 2013.

### Record Status - monthly file only
Indicates additions, changes and deletions to the records.
- A = Addition
- C = Change
- D = Delete

Note:
where a transaction changes category type due to misallocation (as above) it will be deleted from the original category type and added to the correct category with a new transaction unique identifier.
