<script>
    // @ts-nocheck

    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}{/snippet}

        {#snippet scrolly()}
            <ArticleText></ArticleText>
        {/snippet}
    </Scroller>
</div>
