<script>
    import '../css/main.css'
    import data from '../data/data.js'
    import category_data from '../data/category_data.js'
</script>

<div class="main">

        {#each Object.keys(category_data) as key}
        <a href="/about">
        <div class="category_item">
            <img src={category_data[key].picture} alt=""/>
            <h3>{category_data[key].name}</h3>
        </div>
        </a>
        {/each}

</div>