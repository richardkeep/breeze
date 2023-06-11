NOTES:
# Installation
First create a new Laravel app.
`laravel new my-awesome-app`

Install the NPM dependencies
`npm run dev`

Install Laravel Breeze and choose my favourite stack: React JS
```php
composer require laravel/breeze --dev
php artisan breeze:install vue
``` 

# Data Visualization Library 
Then to create a data visualization library, I would install ChartJS (https://www.chartjs.org/) which allows you to create various types of charts.

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

Tweak the charts to ensure it displays all the key information required.

## Deployment
For my daily tasks, I usually deploy using https://forge.laravel.com/
It allows you to deploy provision a server and it installs all the necessary services for Laravel project. (PHP, MySQL, Nginx, etc)
