# How to show tooltip on the disabled cell in WPF DataGrid (SfDataGrid)
You can show tooltip for the disabled [GridCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCell.html?_gl=1*c3a47u*_ga*NzY2NDkwMTMwLjE2NTA1MzA5NTc.*_ga_WC4JKKPHH0*MTY2Nzk3OTI3NC4yOTIuMS4xNjY3OTgwMzMwLjAuMC4w&_ga=2.179406244.1225195101.1667794112-766490130.1650530957) in [WPF DataGrid](https://www.syncfusion.com/wpf-controls/datagrid) (SfDataGrid) by writing style and enabling [ToolTipService.ShowOnDisabled](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.tooltipservice.showondisabled?view=netframework-4.7.2).

Refer to the [ToolTip](https://help.syncfusion.com/wpf/datagrid/tooltip) documentation for more details.

## XAML

```XAML
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="False"
                       ItemsSource="{Binding Path=OrdersDetails}"
                       ColumnSizer="Auto"
                       ShowToolTip="true">
            
      <syncfusion:SfDataGrid.Columns>
           <syncfusion:GridTextColumn MappingName="OrderID" />
           <syncfusion:GridTextColumn MappingName="CustomerID" />
           <syncfusion:GridTextColumn MappingName="ShipCountry" >
              <syncfusion:GridTextColumn.CellStyle>
                  <Style TargetType="syncfusion:GridCell" >
                       <Setter Property="IsEnabled" Value="False" />
                       <Setter Property="ToolTip" >
                            <Setter.Value>
                                 <TextBlock Text="{Binding ShipCountry}" 
                                            Foreground="Red" 
                                            ToolTipService.IsEnabled="True" 
                                            ToolTipService.ShowOnDisabled="True"/>
                             </Setter.Value>
                        </Setter>
                        <Setter Property="ToolTipService.IsEnabled" Value="True" />
                        <Setter Property="ToolTipService.ShowOnDisabled" Value="True" />
                  </Style>
              </syncfusion:GridTextColumn.CellStyle>
           </syncfusion:GridTextColumn>           
           <syncfusion:GridTextColumn MappingName="Freight" />
           <syncfusion:GridCheckBoxColumn HeaderText="Closed" MappingName="IsClosed" />
      </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
```
 
