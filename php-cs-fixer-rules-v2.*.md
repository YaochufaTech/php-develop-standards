
# Basic php-cs-fixer rules
# this rule is suitable for php-cs-fixer v2.*

```php
<?php

/*
 * This file is part of PHP CS Fixer.
 *
 * (c) Fabien Potencier <fabien@symfony.com>
 *     Dariusz Rumiński <dariusz.ruminski@gmail.com>
 *
 * This source file is subject to the MIT license that is bundled
 * with this source code in the file LICENSE.
 */

$header = <<<'EOF'
This file is part of PHP CS Fixer.

(c) Fabien Potencier <fabien@symfony.com>
    Dariusz Rumiński <dariusz.ruminski@gmail.com>

This source file is subject to the MIT license that is bundled
with this source code in the file LICENSE.
EOF;

return PhpCsFixer\Config::create()
    ->setRiskyAllowed(true)
    ->setRules([
        '@Symfony'                            => true,
        '@Symfony:risky'                      => true,
        'combine_consecutive_unsets'          => true,
        //'header_comment'                      => ['header' => $header],
        'array_syntax'                        => ['syntax' => 'short'],
        'no_extra_consecutive_blank_lines'    => ['break', 'continue', 'extra', 'return', 'throw', 'use', 'parenthesis_brace_block', 'square_brace_block', 'curly_brace_block'],
        'no_useless_else'                     => true,
        'no_useless_return'                   => true,
        'ordered_class_elements'              => true,
        'ordered_imports'                     => true,
        'php_unit_strict'                     => true,
        'phpdoc_add_missing_param_annotation' => true,
        'psr4'                                => true,
        'strict_comparison'                   => true,
        'strict_param'                        => true,

        'binary_operator_spaces'              => ['align_double_arrow' => true, 'align_equals' => true],
        'concat_space'                        => ['spacing' => 'one'],
        'no_empty_statement'                  => true,
        'simplified_null_return'              => true,
        'no_extra_consecutive_blank_lines'    => true,
    ])

    ->setFinder(
        PhpCsFixer\Finder::create()
            ->files()
            ->name('*.php')
            ->exclude('vendor')
            ->exclude('PHPExcel')
            ->in(__DIR__)
            ->setUsingCache(false)
    );




```