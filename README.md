# Print Order PDF documentation

The application uses its own editor to create the template. This article will help you in creating/modifying a template

## How to use HTML content option

The "HTML content" field contains the content of the selected block. You can use any HTML tags. You can also set the <style> tag with your own settings. You can also use specified variables, which will be replaced with real values when generating a PDF file. The list of available variables is listed at the bottom of the editor.
Example HTML block:

```
<style>.totals-block {display: flex;justify-content: space-between;width: 100%;}</style>
<h2>Order Totals</h2>
<div class="totals-block">
    <div>Subtotal</div>
    <div>{{totals_subtotal}}</div>
</div>
<div class="totals-block">
    <div>Shipping</div>
    <div>{{totals_shipping}}</div>
</div>
<div class="totals-block">
    <div>Tax</div>
    <div>{{totals_tax}}</div>
</div>
<div class="totals-block">
    <div>Discount</div>
    <div>{{totals_discount}}</div>
</div>
<div class="totals-block">
    <div>
        <strong>Grand Total</strong>
    </div>
    <div>
        <strong>{{grand_total}}</strong>
    </div>
</div>
```

## How to use Custom CSS option

The CSS custom field displays the specified styles of the selected block. You can also add your own styles or change existing ones. The specified styles are applied to the entire block.

## How to create/update Product items block

When generating a block of products, the application uses the following classes: **product-container** and **product-row**. The application copies the block from the **product-row** class, replaces the variables with product values. Repeats this as many times as the number of products the order contains. After that. the result is placed in a block with the **product-container** class. The default is table. But you can create your own design, the main thing is to use the specified classes. Example HTML block of Product Items:
```
<style>table.product-items {width: 100%} table.product-items, .product-items th, .product-items td {border: 1px solid #000;border-collapse: collapse;padding:5px}</style>
<table class="product-items">   <thead>
      <tr>
        <th>Product Name</th>
        <th>SKU</th>
        <th>Price</th>
        <th>Qty</th>
        <th>Subtotal</th>
      </tr>
    </thead>
    <tbody class="product-container">
       <tr class="product-row">
           <td>{{product_name}}</td>
           <td>{{product_sku}}</td>
           <td>{{product_price}}</td>
           <td>{{product_ordered_qty}}</td>
           <td>{{product_subtotal}}</td>
       </tr>
   </tbody>
</table>
```


## How to create/update Totals block

Each platform provides variable list with totals. You can use them in any order with any styles and additional blocks. When generating a PDF, the variables will be replaced with values.
