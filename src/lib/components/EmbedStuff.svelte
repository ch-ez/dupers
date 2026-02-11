<script>
	import dupersUnited from '$lib/assets/dupers-united.png';

	let {
		title = 'DupersUnited - Taking a stand against predatory P2W gambling',
		description = 'We break the economy to fix the game. Taking a stand against predatory P2W gambling.',
		keywords = 'DupersUnited, Duping, DuperTrooper, Dupe, Minecraft Dupe, Minecraft, Anti-P2W, Gaming, Server Economy',
		image = dupersUnited,
		url = 'https://dupers.wtf/',
		type = 'website',
		siteName = 'DupersUnited',
		twitterHandle = '@dupersunited',
		publishedTime = '',
		modifiedTime = '',
		article = false
	} = $props();
</script>

<svelte:head>
	<title>{title}</title>
	<meta content={title} name="title" />
	<meta content={description} name="description" />
	<meta content={keywords} name="keywords" />
	<link href={url} rel="canonical" />

	<meta content={article ? 'article' : type} property="og:type" />
	<meta content={url} property="og:url" />
	<meta content={title} property="og:title" />
	<meta content={description} property="og:description" />
	<meta content={image} property="og:image" />
	<meta content={title} property="og:image:alt" />
	<meta content={siteName} property="og:site_name" />
	<meta content="en_US" property="og:locale" />
	{#if image}
		<meta property="og:image:width" content="1200" />
		<meta property="og:image:height" content="630" />
		<meta property="og:image:type" content="image/png" />
	{/if}
	{#if article}
		{#if publishedTime}
			<meta property="article:published_time" content={publishedTime} />
		{/if}
		{#if modifiedTime}
			<meta property="article:modified_time" content={modifiedTime} />
		{/if}
		<meta property="article:author" content="DupersUnited" />
	{/if}

	<meta content="summary_large_image" name="twitter:card" />
	<meta content={url} name="twitter:url" />
	<meta content={title} name="twitter:title" />
	<meta content={description} name="twitter:description" />
	<meta content={image} name="twitter:image" />
	<meta content={title} name="twitter:image:alt" />
	<meta content={twitterHandle} name="twitter:site" />
	<meta content={twitterHandle} name="twitter:creator" />

	<meta content="DupersUnited" name="application-name" />
	<meta content="DupersUnited" name="apple-mobile-web-app-title" />
	<meta content="yes" name="apple-mobile-web-app-capable" />
	<meta content="black-translucent" name="apple-mobile-web-app-status-bar-style" />
	<meta content="yes" name="mobile-web-app-capable" />

	{@html `<script type="application/ld+json">${JSON.stringify({
		'@context': 'https://schema.org',
		'@type': article ? 'Article' : 'WebSite',
		name: title,
		description: description,
		url: url,
		image: image,
		publisher: {
			'@type': 'Organization',
			name: 'DupersUnited',
			logo: {
				'@type': 'ImageObject',
				url: image
			}
		},
		...(article && publishedTime ? { datePublished: publishedTime } : {}),
		...(article && modifiedTime ? { dateModified: modifiedTime } : {})
	})}<\/script>`}
</svelte:head>
