# How to customize filter popup menu in Flutter DataGrid (SfDataGrid)? 

In this article, we will show how to customize filter popup menu in [Flutter DataGrid](https://www.syncfusion.com/flutter-widgets/flutter-datagrid).

Initialize the [SfDataGrid](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/SfDataGrid-class.html) widget with its necessary properties. To apply custom colors and personalize the filter popup menu, configure the properties through the [SfDataGridTheme](https://pub.dev/documentation/syncfusion_flutter_core/latest/theme/SfDataGridTheme-class.html). To enable this functionality, ensure that your SfDataGrid is wrapped inside an SfDataGridTheme widget. Both the SfDataGridThemeData and SfDataGridTheme classes are available in the [syncfusion_flutter_core](https://pub.dev/packages/syncfusion_flutter_core) package. Make sure to import this package before using these features.

```dart
import 'package:syncfusion_flutter_datagrid/datagrid.dart';
import 'package:syncfusion_flutter_core/theme.dart';

@override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Syncfusion Flutter DataGrid')),
      body: SfDataGridTheme(
        data: SfDataGridThemeData(
          filterPopupBackgroundColor: Colors.blue[50],
          filterPopupCheckboxFillColor: WidgetStatePropertyAll(
            Colors.green[400],
          ),
          filterPopupDisabledIconColor: Colors.teal[400],
          okFilteringLabelColor: Colors.white,
          okFilteringLabelButtonColor: Colors.indigo[600],
          cancelFilteringLabelColor: Colors.black,
          cancelFilteringLabelButtonColor: Colors.blueGrey[200],
        ),
        child: SfDataGrid(
          source: employeeDataSource,
          columnWidthMode: ColumnWidthMode.fill,
          allowFiltering: true,
          columns: <GridColumn>[
            GridColumn(
              columnName: 'id',
              label: Container(
                padding: EdgeInsets.all(16.0),
                alignment: Alignment.center,
                child: Text('ID'),
              ),
            ),
            GridColumn(
              columnName: 'name',
              label: Container(
                padding: EdgeInsets.all(8.0),
                alignment: Alignment.center,
                child: Text('Name'),
              ),
            ),
            GridColumn(
              columnName: 'designation',
              label: Container(
                padding: EdgeInsets.all(8.0),
                alignment: Alignment.center,
                child: Text('Designation', overflow: TextOverflow.ellipsis),
              ),
            ),
            GridColumn(
              columnName: 'salary',
              label: Container(
                padding: EdgeInsets.all(8.0),
                alignment: Alignment.center,
                child: Text('Salary'),
              ),
            ),
          ],
        ),
      ),
    );
  }
```

You can download this example on [GitHub](https://github.com/SyncfusionExamples/How-to-customize-filter-popup-menu-in-Flutter-DataGrid).