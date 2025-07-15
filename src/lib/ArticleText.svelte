<script>
    let { children } = $props();
</script>

<div class="article-card">
    <div class="article-text">
        <p>
            {@render children()}
        </p>
    </div>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 75%;
        background-color: #b99095;
        color: white;
        border: solid #fcb5ac 3px;
        border-radius: 20px;
        padding: 20px;
        box-shadow: 16px 16px black;
        font-family: "Times New Roman", Times, serif;
    }
    .article-card {
        background-color: #458883;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 2rem;
        box-sizing: border-box;
        font-family: "Inter", sans-serif;
    }
</style>
