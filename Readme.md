<!-- default file list -->
*Files to look at*:

* [Index.razor](./CS/BlazorProject/Pages/Index.razor)
<!-- default file list end -->

### DataGrid for Blazor - How to create DataGrid and its columns at runtime
<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/230140164/)**
<!-- run online end -->

This example shows how to create DataGrid components at runtime and create its columns dynamically.
The easiest way to do so is to write a method that returns the **RenderFragment\<T\>** object, for example, in the following manner:
```
RenderFragment<DataItem> buildGridsWithColumns = (dataObject) =>
@{ RenderFragment<DataItem> buildGridsWithColumns = (dataObject) =>
    @<DxDataGrid CssClass="mw-1100" @ref="grid" Data="@dataObject.Data">
        <Columns>

            @foreach (var column in dataObject.ColumnNames)
            {
                <DxDataGridColumn @key="@column" Caption="@column" Field="@column" Width="400px" />}
        </Columns>
    </DxDataGrid>; }
```
The call of such a method creates a grid with columns.
