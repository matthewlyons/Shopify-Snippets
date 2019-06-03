# Options As Buttons 

This snippet allows you to switch from dropdowns to buttons for each option. 

To do this it outputs each value in each option set as a button with the option name as its name and its value as it's value. 

When clicked JavaScript sets the variable of the option name to the value:

``` bash
window[$(this).attr('name')] = $(this).val();
```

Once all option variables have values JavaScript will select the correct dropdown by finding the matching data attribute:
``` bash
$(".ProductVariant{% for product_option in product.options_with_values %}[data-{{ product_option.name | remove: " " | remove: " ? " }}='" + {{ product_option.name | remove: " " | remove: "?" }} + "']{% endfor %}").click();
```