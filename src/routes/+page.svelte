<script>
	import {
		Table,
		TableBody,
		TableBodyCell,
		TableBodyRow,
		TableHead,
		TableHeadCell
	} from 'flowbite-svelte';
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
</script>

<Table>
	<TableHead>
		<TableHeadCell>할 일 </TableHeadCell>
		<TableHeadCell>action</TableHeadCell>
	</TableHead>
	<TableBody class="divide-y">
        {#each todo as item}
            <TableBodyRow>
                <TableBodyCell>{item.content}</TableBodyCell>
                <TableBodyCell>{item.status}</TableBodyCell>
            </TableBodyRow>
        {/each}
	</TableBody>
</Table>
