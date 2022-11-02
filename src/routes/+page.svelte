<h1 class="text-2xl">citation generator</h1>
cuma support vancouver dulu maap
<div class="flex flex-col w-96 mx-auto gap-2">
    <input type="text" placeholder="Title" bind:value={title} class="border-2 px-2 rounded-full"/>
    <input type="text" placeholder="Author" bind:value={author} class="border-2 px-2 rounded-full"/>
    <input type="text" placeholder="Journal Name" bind:value={journalName} class="border-2 px-2 rounded-full"/>
    <input type="text" placeholder="Year" bind:value={year} class="border-2 px-2 rounded-full"/>
    <input type="text" placeholder="Volume" bind:value={volume} class="border-2 px-2 rounded-full"/>
    <input type="text" placeholder="Issue" bind:value={issue} class="border-2 px-2 rounded-full"/>
    <input type="text" placeholder="Page" bind:value={page} class="border-2 px-2 rounded-full"/>
    <input type="text" placeholder="DOI" bind:value={doi} class="border-2 px-2 rounded-full"/>
    <input type="text" placeholder="Availablilty" bind:value={availability} class="border-2 px-2 rounded-full"/>
    <input type="date" placeholder="Date" bind:value={date} class="border-2 px-2 rounded-full"/>
</div>

<span class="text-center">
    {author}. {title}, {journalName} {year}; {volume}({issue}):{page}. {#if doi}doi: {doi}{/if}. {availability} [{formattedDate}]
</span>



<script>
    let title = '';
    let author =""
    let journalName =""
    let year =""
    let volume =""
    let issue =""
    let page =""
    let doi =""
    let availability =""
    let date = new Date().toISOString()

    $: formattedDate = new Date(date).toLocaleDateString('id-ID', {
        year: 'numeric',
        month: 'long',
        day: 'numeric'
    });

</script>