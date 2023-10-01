<script>	
    import Modal from './Modal.svelte';

	let showModal = false;

	let items = []

    let count = 0

    function new_param() {
		count += 1

        items = [...items, {"name": "add"}];
	}
</script>

<div class="form_content">
    <div class="new_param_box">
        {#each items as item}
		    <div class="new_parametr">{item.name}</div>
	    {/each}
    </div>
    <div class="but_add">
        <button on:click={() => (showModal = true)} class="but_add_params" type="submit">
            <span>Добавить</span>
        </button>
    </div>
    <Modal bind:showModal></Modal>
</div>

<style>
	.form_content {
        display: grid;
        grid-template-columns: 4fr 1fr;

        margin: 10px;
        padding: 10px;

        background-color: white;
        border-radius: var(--border-r);
        border: 1px solid var(--color-bg);
        box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3);
    }

    .but_add {
        display: grid;
        justify-content: end;
        align-items: center;
    }

    .but_add_params {
        background-color: var(--main-color);
        border-radius: var(--border-r);
        border: none;
        width: 80px;
        height: 40px;
        color: white;

        font-weight: bold;
        font-size: 14px;
    }

    .but_add_params:hover {
        background-color: var(--main-color);
    }

    .but_add_params span {
        display: inline-block;
    }

    .but_add_params:active span {
        transform: translateY(2px); /* Сдвиг текста внутри кнопки вниз при нажатии */
    }

    .new_param_box {
        display: grid;
        align-items: center;
        grid-template-columns: repeat(auto-fill, minmax(100px, 1fr)); /* автоматически определить количество столбцов и их ширину */
        grid-gap: 10px; /* пространство между блоками */
    }

    .new_parametr {
        background-color:var(--main-color);
        color: white;
        border-radius: var(--border-r);
        width: 80px;
        height: 40px;
        
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>