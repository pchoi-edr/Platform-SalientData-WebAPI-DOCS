# Salient Data Format

Data Fields for Salient data should be categorized according to their `Category`. Category lists are as follows:

```
1. Identifer
2. Property
3. MultiFamily
4. Appraisal
5. Valuation
6. Misc
7. SalesData
8. SalesComps
9. RetailOfficeIndustrialTenants
10. HealthcareFinanceSeniorHousing
```

Category List references are case sensitive, with no spaces, and no special characters.

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
    },
    { ... }
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



