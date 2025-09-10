# How to show tooltip on the disabled cell in WPF DataGrid?

In [WPF DataGrid](https://www.syncfusion.com/wpf-controls/datagrid) (SfDataGrid), you can show tooltip for the disabled [GridCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCell.html) by writing style and enabling **ToolTipService.ShowOnDisabled**.

```xml
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
           <syncfusion:GridCheckBoxColumn HeaderText="Closed"
                                          MappingName="IsClosed" />
      </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
```

Take a moment to peruse the [WPF DataGrid - ToolTip](https://help.syncfusion.com/wpf/datagrid/tooltip) documentation, to learn more about tooltip with examples.
