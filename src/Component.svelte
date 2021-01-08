<script>
  import { siteURL, siteAuthor, siteIndex } from './store'

  export let meta_data = {
    site_url: "https://fakeurl.com",
    site_author: "Fake Author Name",
    site_index: "/index",
    title: undefined,
    noindex: false,
    nofollow: false,
    description: undefined,
    keywords: undefined,
    canonical: undefined,
    openGraph: undefined,
    twitter: undefined,
  };

  siteURL.set(meta_data.site_url);
  siteAuthor.set(meta_data.site_author);
  siteIndex.set(meta_data.site_index);

  const createArr = (obj) => {
    let arr = Object.keys(obj)
      .map(key => ({
        key: key, 
        data: obj[key]
      }))
    return arr
  }

  const arrayToUse = createArr(meta_data);
</script>

<svelte:head>
  {#each arrayToUse as item}
    {#if item.key == 'openGraph' || item.key == 'twitter'}
      {#each createArr(item.data) as i}
        <meta name={i.key} content={i.data}/>
      {/each}
    {:else if item.key == 'title'}
      <title>{item.data}</title>
		{:else if 
			item.data !== undefined && 
			item.data !== false && 
			item.key !== "site_url" && 
			item.key !== "site_author" && 
			item.key !== "homepage"
		}
    	<meta name={item.key} content={item.data} />
		{/if}
  {/each}
</svelte:head>