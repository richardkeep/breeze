NOTES:

To create a data visualization library, I would install ChartJS (https://www.chartjs.org/) which allows you to create various types of charts.

To get started very quickly, I will start by installing ChartJS Package using this package https://github.com/LaravelDaily/laravel-charts

`composer require laraveldaily/laravel-charts`

Then configure the chart as follows:
```php
$chart_options = [
    'chart_title' => 'Academic Results by months',
    'report_type' => 'group_by_date',
    'model' => 'App\Models\AcademicReport',
    'group_by_field' => 'created_at',
    'group_by_period' => 'month',
    'chart_type' => 'bar',
];
$my_chart = new LaravelChart($chart_options);

return view('chart', compact('my_chart'));
```
then render the bar chart using
`{!! $my_chart->renderHtml() !!}`
