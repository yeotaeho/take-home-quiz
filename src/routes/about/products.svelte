<script>
    import products_data from './data/products_data.js';
    import './css/Products.css';

    for (const key in products_data) {
    if (products_data.hasOwnProperty(key)) {
        products_data[key].price = products_data[key].price.toString().replace(/\B(?=(\d{2})+(?!\d))/g, ".")
    }
}
</script>

<div class="title">
    <a href="/"><input type="button" value="←"></a>
    <h1>Appetizers<span>Salad and fries</span></h1>
</div>
<div class="products">
    {#each Object.keys(products_data) as key}
        <div class="products_item">
            <img src={products_data[key].picture} alt=""/>
            <h6>{products_data[key].name}</h6>
            <p>${products_data[key].price}</p>
        </div>
    {/each}
</div>
