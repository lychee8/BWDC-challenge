<script>
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<ArticleText>
    <h1>
        Let's take a look at this chart and data created and collected by the
        Black Wealth Data Center
    </h1>

    <link
        rel="stylesheet"
        href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200&icon_names=keyboard_arrow_down"
    />

    <button class="down-arrow"
        ><span class="material-symbols-outlined">keyboard_arrow_down</span
        ></button
    >
</ArticleText>

<style>
    .down-arrow {
        background-color: #b99095;
        border-color: #b99095;
    }

    .material-symbols-outlined {
        color: white;
    }
</style>
