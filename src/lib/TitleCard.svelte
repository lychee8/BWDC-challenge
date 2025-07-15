<script>
    let { title, subtitle } = $props();
</script>

<div class="title-card">
    <div class="content">
        <h1>{title}</h1>
        <p>{subtitle}</p>
    </div>
</div>

<style>
    .title-card {
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

    .content {
        max-width: 700px;
        background-color: #b99095;
        padding: 2rem;
        border: 6px solid #fcb5ac;
        border-radius: 2rem;
        box-shadow: 16px 16px;
        font-family: "Times New Roman", Times, serif;
    }

    h1 {
        font-size: 3rem;
        margin: 0;
        color: #f8f8f4;
        /* text-shadow: 1px 1px 0 #007052; */
        font-family: "Times New Roman", Times, serif;
    }

    p {
        font-size: 2rem;
        color: #f7f5eb;
        margin-top: 1rem;
    }

    @media (max-width: 600px) {
        h1 {
            font-size: 2.2rem;
        }

        p {
            font-size: 1.1rem;
        }
    }
</style>
