# Salient Data Fields

> All fields are Strings, unless otherwise indicated.

| Category | Field Name | Field Name Descr | Notes |
| :--- | :--- | :--- | :--- |
| Identifier | ProperID | Property ID |  |
| Identifier | LocationID | Location ID |  |
| Identifier | StreetNumber | Street Number |  |
| Identifier | StreetName | Street Name |  |
| Identifier | City | City |  |
| Identifier | State | State |  |
| Identifier | ZipCode | Zip Code |  |
| Identifier | County | County |  |
| Identifier | AssessorParcelNumber | Assessor Parcel Number\(s\) |  |
| Identifier | BlockNumber | Block \# |  |
| Identifier | LotNumber | Lot \# |  |
| Identifier | LatLong | Lat/Long |  |
| Property | Type | Property Type |  |
| Property | SubType | Property Sub Type |  |
| Property | ResidentialUnits | \# of Units Residential | Integer |
| Property | CommercialUnits | \# of Units Commerical | Integer |
| Property | BuildingClass | Building Class |  |
| Property | Condition | Condition | enum \[ POOR, FAIR, GOOD, LIKENEW, NEW \] |
| Property | YearBuilt | Year Built | Integer |
| Property | YearRenovated | Year Renovated | Integer |
| Property | GrossBuildingArea | Gross Building Area in SQFT | Object: { area: integer, uom: enum \[SQFT, SQMT\] } |
| Property | GrossLivingArea | Gross Living Area in SQFT | Object: { area: integer, uom: enum \[SQFT, SQMT\] } |
| Property | RentableArea | Rentable Area in SQFT | Object: { area: integer, uom: enum \[SQFT, SQMT\] } |
| Property | GrossLeaseable | Gross Leaseable in SQFT | Object: { area: integer, uom: enum \[SQFT, SQMT\] } |
| Property | LandArea | Land Area in Acres | Array of Objects: { area: integer, uom: enum \[SQFT, ACRE, SQMT\] } |
| Property | ClearHeight | Clear Height |  |
| Property | PercentOffice | Percent Office |  |
| Property | Elevators | \# of Elevators | Integer |
| Property | GreenStatus | Green Status |  |
| Property | PropertyRightsAppraised | Property Rights Appraised |  |
| Property | HighestBestUse | Highest and Best Use? |  |
| Property | TaxAssessedValue | Real Estate Tax Assessed Value |  |
| Property | TaxRate | Tax Rate |  |
| Property | TaxYear | Tax Year | Integer |
| Property | OperatingExpense | Operating Expense \(%\) | Ex: 60% |
| MultiFamily | UnitType | Unit Type |  |
| MultiFamily | Units | \# of Units per Unit Type |  |
| MultiFamily | AvgUnitSize | Avg Unit Size \(sq.ft\) of each Unit Type |  |
| MultiFamily | AvgInPlaceRent | Avg In Place Rent per Unit Type |  |
| MultiFamily | AvgRent | Avg Asking Rent per Unit Type |  |
| MultiFamily | Buildings | \# of Buildings | Integer |
| MultiFamily | Floors | \# of Floors in each Building |  |
| MultiFamily | AirConditioning | Air Conditioning |  |
| MultiFamily | CommonAreaLaundry | Common Area Laundry |  |
| MultiFamily | Parking | Parking | Array of Parking types: \[ 'Non-Garage', 'Garage', 'Covered', ... \] |
| Appraisal | EffectiveDate | Appraisal Effective As of Date |  |
| Appraisal | ReportDate | Appraisal Report Date |  |
| Appraisal | InspectionDate | Inspection Date |  |
| Appraisal | CompanyName | Appraisal Company Name |  |
| Appraisal | AppraiserName | Appraiser Name |  |
| Appraisal | City | Appraiser City |  |
| Appraisal | State | Appraiser State |  |
| Appraisal | Zip | Appraiser Zip |  |
| Appraisal | ValuationTrailing | Valuation Premise Trailing 12 Month |  |
| Appraisal | ValuationProspective | Valuation Premise Prospective 12 Month |  |
| Appraisal | StartDate | 12 Month Start Date |  |
| Appraisal | EndDate | 12 Month End Date |  |
| Valuation |  | Valuation A - XX |  |
| Valuation |  | Valuation A - XX - Basis |  |
| Valuation |  | Valuation A - XX - Value |  |
| Valuation |  | Valuation A - XX - Date |  |
| Valuation |  | Going Concern Value |  |
| Valuation |  | Valuation A - XX - Real Property / Value of the Building Value\($\) |  |
| Valuation |  | Valuation A - XX - Contributory Personal Property / FF& E Value\($\) |  |
| Valuation |  | Valuation A - XX - Business Enterprise Value \($\) |  |
| Valuation |  | FF & E |  |
| Valuation |  | Income Valuation - Potential  Gross Income\($\) |  |
| Valuation |  | Income Valuation - Operating Expense Ratio\(%\) |  |
| Valuation |  | Income Valuation - Effective Gross Income\($\) |  |
| Valuation |  | Income Valuation - Total Operating Expenses\($\) |  |
| Valuation |  | Income Valuation - Net Operating Income\($\), Year 1 of DCF |  |
| Valuation |  | Income Valuation - Net Operating Income\($\), Direct Cap |  |
| Valuation |  | Income Valuation - Vacancy Rate |  |
| Valuation |  | Income Valuation - Overall Capitalization Rate |  |
| Valuation |  | Income Valuation - Terminal Capitalization Rate |  |
| Valuation |  | Income Valuation - Discount Rate |  |
| Valuation |  | Income Valuation - Yield Rate |  |
| Valuation | AggregateRetailValue | Aggregate Retail Value |  |
| Valuation | GrossSelloutValue | Gross Sellout Value |  |
| Valuation | NetSelloutValue | Net Sellout Value |  |
| Valuation | DiscountedNetSelloutValue | Discounted Net Sellout Value |  |
| Valuation | RentalFallbackValue | Rental Fallback Value |  |
| Valuation | InvestmentValue | Investment Value |  |
| Valuation | InsurableValue | Insurable Value |  |
| Valuation | ReplacementCostValue | Replacement Cost Value |  |
| Valuation | LiquidationValue | Liquidation Value |  |
| Valuation | DispositionValue | Disposition Value |  |
| Valuation | ValueinUse | Value in Use |  |
| Valuation |  | \(GRM\) Gross Rent Multiplier |  |
| Valuation |  | \(EGIM\) Effective Gross Income Multiplier |  |
| Valuation | LandValue | Land Value |  |
| Valuation | AdditionalIncome | Additional Income |  |
| Valuation | AnnualIncome | Annual Income |  |
| Valuation | ContributoryValue | Contributory Value |  |
| Valuation |  | Prospective Value, as Stable |  |
| Valuation |  | Prospective Value, as Complete |  |
| Valuation |  | Prospective Value, as Is |  |
| Valuation |  | Go Dark Value \(single tenant only\) |  |
| Valuation |  | Hypothetical Value, assuming stable today |  |
| Misc |  | Prospective As Stablized Value with or without 421a Tax Exemption Benefits |  |
| Misc |  | Prospective As Stablized Value with or without J-51 Abatement Benefits |  |
| Misc |  | Prospective As Stablized Value with or without \(ICAP\) Industrial Commercial Exemption Program Benefits |  |
| Misc |  | Market Value of the Air Rights |  |
| SalesData | PreviousSalesPrice | Known Previous Sales |  |
| SalesData | LastTransactionDate | Last Transaction Date |  |
| SalesData | LastTransactionPrice | Last Transaction Price |  |
| SalesData | ListingDate | Actual Listing Date |  |
| SalesData | ListingPrice | Actual Listing Price |  |
| SalesComps | Address | Address |  |
| SalesComps | Price | Price |  |
| SalesComps | Units | Size of building \(\# units\) |  |
| SalesComps | Age | Age |  |
| SalesComps | Occupancy | Occupancy |  |
| SalesComps | ValuePer | $/ unit or sq ft |  |
| SalesComps | CapRate | Cap rate |  |
| SalesComps | Date | Date |  |
| SalesComps | PropertyType | Property type |  |
| SalesComps | SubPropertyType | Sub-Property Type |  |
| SalesComps | LatLong | Lat/Long |  |
| SalesComps | ADR | ADR |  |
| SalesComps | RevPAR | RevPAR |  |
| SalesComps | OER | OER |  |
| SalesComps | ExitRental | Exit rental info |  |
| RetailOfficeIndustrialTenants | AnchorTenents | \# of Anchor Tenants | Integer |
| RetailOfficeIndustrialTenants | AnchorTenantName | Major / Anchor Tenant Name |  |
| RetailOfficeIndustrialTenants | AnchorPercentRentable | Major / Anchor % of Rentable SQFT | Array of Object: { rent: integer, uom: enum } |
| RetailOfficeIndustrialTenants | AnchorAvgInPlaceRent | Major / Anchor Avg In Place Rent per SQFT | Array of Object: { rent: integer, uom: enum } |
| RetailOfficeIndustrialTenants | AnchorAvgAskRent | Major / Anchor Avg Ask Rent per SQFT | Array of Object: { rent: integer, uom: enum } |
| RetailOfficeIndustrialTenants | NumberNonTenents | \# of Non-Major Tenants | Integer |
| RetailOfficeIndustrialTenants | NonPercentRentable | Non-Major % of Rentable SQFT | Array of Object: { rent: integer, uom: enum } |
| RetailOfficeIndustrialTenants | NonAvgInPlaceRent | Non-Major Avg In Place Rent per SQFT | Array of Object: { rent: integer, uom: enum } |
| RetailOfficeIndustrialTenants | NonAvgAskRent | Non-Major Avg Ask Rent per SQFT | Array of Object: { rent: integer, uom: enum } |
| RetailOfficeIndustrialTenants | AvgSales | Avg Sales per SQFT | Array of Object: { rent: integer, uom: enum } |
| RetailOfficeIndustrialTenants | CAMExpenses | CAM expenses |  |
| RetailOfficeIndustrialTenants | OwnerOccupied | Owner Occupied? | Boolean |
| HealthcareFinanceSeniorHousing | Beds | \# of Beds | Integer |
| HealthcareFinanceSeniorHousing | Rooms | \# of Rooms | Integer |
| HealthcareFinanceSeniorHousing | PerSQFT | Per Square Foot |  |
| HealthcareFinanceSeniorHousing | EGIMAnalysis | EGIM Analysis |  |
| HealthcareFinanceSeniorHousing | RealPropertyValue | Real Property / Value of the Building Value\($\) | Integer |
| HealthcareFinanceSeniorHousing | ContributoryPersonalFFEValue | Contributory Personal Property / FF& E Value\($\) | Integer |
| HealthcareFinanceSeniorHousing | BusinessEnterpriseValue | Business Enterprise Value \($\) | Integer |

Data Fields for Salient data should be categorized according to their `Category`.

##### For Example:

> JSON

```
{
    Identifier: {
        ProperID: 123,
        LocationID: 123,
        { ... }
    },
    Property: {
        Type: 'Multi-Residential',
        SubType: 'Commercial'
    }
}
```

> XML

```
<?xml version="1.0" encoding="UTF-8"?>
<root>
   <Identifier>
      <LocationID>123</LocationID>
      <ProperID>123</ProperID>
   </Identifier>
   <Property>
      <SubType>Commercial</SubType>
      <Type>Multi-Residential</Type>
   </Property>
</root>
```



