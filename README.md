# Add an Azure subnet to an existing Azure Virtual Network with PowerShell

Run the following commands in PowerShell to add a subnet to an existing Azure Virtual Network

```PowerShell
# Gather our existing Azure vNet
$vNet = Get-AzVirtualNetwork -Name 'vNetName' -ResourceGroup 'vnet-rg-name'

# Replace the following required Azure Virtual Network variables
$subNet = @{
    Name = 'your-subnet-name'
    AddressPrefix = 'your-address-prefix' #e.g. '10.0.0.0/24'
}

# Add the subnet to our Azure Virtual Network
$virtualNetwork | Add-AzVirtualNetworkSubnetConfig -Name $subNet.Name -AddressPrefix $subNet.AddressPrefix
$virtualNetwork | Set-AzVirtualNetwork
```

## Notes

## Troubleshooting

## Alternatives

## Additional Resources

- [MS | Docs | Get-AzVirtualNetwork][1]
- [MS | Docs | Add-AzVirtualNetworkSubnetConfig][2]
- [MS | Docs | Set-AzVirtualNetwork][3]

<!-- Reference Links -->

[1]: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azvirtualnetwork?view=azps-5.7.0
[2]: https://docs.microsoft.com/en-us/powershell/module/az.network/add-azvirtualnetworksubnetconfig?view=azps-5.7.0
[3]: https://docs.microsoft.com/en-us/powershell/module/az.network/set-azvirtualnetwork?view=azps-5.7.0
