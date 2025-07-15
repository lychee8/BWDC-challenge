<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    const options = {
        threshold: [0.85, 0.95],
    };

    const callback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                <img
                    src="https://images.unsplash.com/photo-1599041125553-a3b967646ca5?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTZ8fGJsYWNrJTIwd29tYW4lMjBjb2Rpbmd8ZW58MHx8MHx8fDA%3D"
                />
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText {callback} {options}>
                <h1>Now we wonder... Why does this happen?</h1>
            </ObservedArticleText>
            <ObservedArticleText {callback} {options}>
                <h1>main idea</h1>
            </ObservedArticleText>

            <ObservedArticleText {callback} {options}>
                <h1>
                    Before we dive into this statement we need to understand an
                    import concept...
                </h1>
            </ObservedArticleText>

            <ObservedArticleText {callback} {options}>
                <h1>Equity vs. Equality</h1>
            </ObservedArticleText>
        {/snippet}
    </Scroller>
</div>

<!-- 
<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    const options = {
        threshold: [0.85, 0.95],
    };

    const callback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                <p>
                    This section shows how to use the
                    <code>{"<ObservedArticleText>"} component.</code>
                </p>
                <img src= "https://images.unsplash.com/photo-1599041125553-a3b967646ca5?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTZ8fGJsYWNrJTIwd29tYW4lMjBjb2Rpbmd8ZW58MHx8MHx8fDA%3D"/>
                
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText {callback} {options}>
                <code>{"<ObservedArticleText>"}</code> example #1
            </ObservedArticleText>

            <ObservedArticleText {callback} {options}>
                <code>{"<ObservedArticleText>"}</code> example #2
            </ObservedArticleText>

            <ObservedArticleText {callback} {options}>
                <code>{"<ObservedArticleText>"}</code> example #3
            </ObservedArticleText>
        {/snippet}
    </Scroller>
</div> -->

<!-- <ObservedArticleText>

    



</ObservedArticleText>

<ArticleText>
   
</ArticleText>

<ArticleText>
    <h1>
        
    </h1>
</ArticleText> -->

<!-- <script>
    import { fade } from 'svelte/transition';
    let visible = $state(true);
</script>


<h1 transition:fade> Now I want to point your attention to this statistic </h1> -->
