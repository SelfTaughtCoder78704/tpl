<script>
    export let ctaLink = "";
	export let ctaText = "";
	export let classes = "";
	export let id = "";
	export let trackable = "";
	export let interaction = "";
	export let ctaFinePrint = "";
	export let ctaRel = "";
</script>

<div class="cta-block {classes}" id={id ? id : ""}>
    <div class="cta-wrapper " >
        <a class="btn" href={ctaLink} 
		data-trackable={trackable} 
		data-interaction={interaction}
		rel={ctaRel ? ctaRel : ""}
		>{ ctaText }</a>
		{#if ctaFinePrint }
			<small class="cta-fine-print">
				{ctaFinePrint}
			</small>
		{/if}
    </div>
</div>

<style>
.cta-block {
	 margin-right: auto;
	 margin-left: auto;
}
 .cta-block .cta-fine-print {
	 margin-top: 0.625rem;
	 text-align: center;
}
 .cta-wrapper {
	 display: inline-block;
}
 .btn {
	 -webkit-appearance: none;
	 padding:  1.25rem;
	 display: inline-block;
	 color: white;
	 background:rgb(0,80,160);
	 font-size: 1rem;
	 line-height: 1;
	 text-align: center;
	 text-decoration: none;
	 font-family: sans-serif;
	 transition: color 300ms, border-color 300ms, background-color 300ms;
}

 .btn:focus {
	 outline: none;
}
 .btn-small {
	 font-size: .8rem;
	 padding: 0.625rem 1.25rem;
}

.btn:hover {
	 background:rgb(214, 27, 27);
	
}
 
</style>