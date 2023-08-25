# Markdown

## Install

```
composer require norman-huth/markdown
```

## Markdown Table Generator

### Basic Usage

Create this table:

```markdown
| ID | Name          |
|:---|:--------------|
| 1  | Administrator |
| 2  | User          |
| 4  | Hugo          |
```

#### Row for Row

```php
use NormanHuth\Markdown\Table;

$table = new Table();

$table->addCell('ID');
$table->addCell('Name');

$table->addRow([1, 'John Doe']);
$table->addRow([2, 'Johanna Doe']);

echo $table->render();
```

#### Array or `\Illuminate\Support\Collection`

```php
use NormanHuth\Markdown\Table;

$table = new Table();

$table->addCell('ID');
$table->addCell('Name');

$table->addRows(
    [
        [1, 'John Doe'],
        [2, 'Johanna Doe'],
    ]
);

echo $table->render();
```

#### Laravel Model Collection

```php
use NormanHuth\Markdown\Table;

$table = new Table();
$table->addCell('ID');
$table->addCell('Name');
$table->addRows(\App\Models\User::all(['id', 'name']));

return $table->render();
```
