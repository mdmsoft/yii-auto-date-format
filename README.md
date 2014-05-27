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
      'class' => 'ext.MdmAutoDateFormatBehavior',
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
