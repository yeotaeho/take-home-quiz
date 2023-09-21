<script>
    import '../css/nav.css'
    import '../css/reset.css'

    const tableNumber = '12'
    const languages = [{name: 'English'}, {name: '한국어'}]
    let toggle = false;
</script>

<div class="nav">
    <ul class="nav_menu">
    <li class="item">
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <span id="language_name" on:click={() => {toggle = !toggle}}>{languages[0].name}</span><img src="./src/img/chevron-down.png" alt="" class:open={toggle} class:closed={!toggle}/>
        <ul class="languages">
            <!-- svelte-ignore missing-declaration -->
            {#each languages as data , dataIndex(dataIndex)}
                <!-- svelte-ignore a11y-click-events-have-key-events -->
                <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
                {#if toggle}
                <li on:click={() => {
                    console.log(languages[dataIndex].name)
                    document.getElementById('language_name').innerHTML = languages[dataIndex].name
                    toggle = false
                }}>{data.name}</li>
                {/if}
  
            {/each}
        </ul>
    </li>
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
        <li on:click={()=>{alert('Waiter Called')}} class="item"><img src="./src/img/notifications_active.png" alt=""/>Call Waiter</li>
        <li class="item"><img src="./src/img/receipt.png" alt=""/>View Bill</li>
        <li class="item"><img src="./src/img/shopping_cart.png" alt=""/>My Cart<span class="count">0</span></li>
        <li class="item"><img src="./src/img/table.png" alt=""/>{tableNumber}</li>
    </ul>
</div>

