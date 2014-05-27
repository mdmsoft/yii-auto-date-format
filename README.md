yii-auto-date-format
====================

Yii1 behavior to automatic convert date format

Instalation
-----------

Download and extract to your extension directory.

Usage
-----
On your ActiveRecord class, add to method `behaviors()`:
```php
function behaviors()
{
    return array(
        'AutoDateFormat' => array(
            'class' => 'ext.MdmAutoDateBehavior',
            'logicalFormat' => 'd-m-Y',
            'physicalFormat' => 'Y-m-d',
            'attributes' => array(
                'orderDate' => 'order_date', // mapping attribute from logical to physical filed.
            ),
        ),
        ...
    );
}
```
Then, for this AR, use attribute `orderDate` instead of `order_date`.
```php
$model->orderDate = '27-05-2014';
```
equivalent with
```php
$model->order_date = '2014-05-27';
```
on your form
```php
$form->widget('zii.widgets.jui.CJuiDatePicker', array(
	'model' => $model,
	'attribute' => 'orderDate',
	'options' => array(
		'showAnim' => 'fold',
		'dateFormat' => 'dd-mm-yy',
	),
	'htmlOptions' => array(
		'style' => 'height:20px;',
		'size' => '12',
	),
));
```