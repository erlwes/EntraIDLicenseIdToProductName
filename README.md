# EntraIDLicenseIdToProductName
Create offline lookup table for getting friendly product name from a licence GUID.

The complete product names and service plan identifiers for licensing in Entra ID and Office 365 is found here:
https://learn.microsoft.com/en-us/entra/identity/users/licensing-service-plan-reference

The script will get the HTML-table from the website, parse it into a PowerShell-Object, and then sace it as a CSV-file for later lookup.

# Example 1 - Lookup a single GUID/SkuID
```PowerShell
.\LicenseIdToProductName.ps1 -GUID '06ebc4ee-1bb5-47dd-8120-11324bc54e06'
```

![image](https://github.com/user-attachments/assets/aa5a6c06-06d2-4e36-b621-c6f692758b3a)


# Example 2 - Display the complete table
```PowerShell
.\LicenseIdToProductName.ps1 -ShowCompleteTable
```

![image](https://github.com/user-attachments/assets/c4666dc2-4e98-40fd-8e56-da55f47252af)
