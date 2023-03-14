<script>
	let todo = [
		{
			content: 'study',
			status: 0
		},
		{
			content: 'dinner',
			status: 1
		}
	];
	let value = '';

	function handler() {
		todo = [...todo, { content: value, status: 0 }];
		value = '';
	}
	//해당 아이템 완성 버튼 클릭
	// @ts-ignore
	function complete(index) {
		todo[index].status = 1;
	}

	//json 문법
</script>

<div>
	<ul>
		{#each todo as item, index}
			<li>
				{#if item.status === 0}
					{item.content}
					<button on:click={() => complete(index)}> complete </button>
					<!-- button 여러개 each 안에 -->
				{:else}
					<strike>{item.content}</strike>
				{/if}
			</li>
		{/each}
	</ul>
	<input bind:value />

	<button on:click={() => handler()}> Add </button>
</div>

<style>
    strike {
        color : red;
    }
</style>