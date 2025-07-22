<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img class="edu1-img" src="edu1.png" alt="Women in a library" />
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h1>
                    Hopefully now you feel that where you are starting in the
                    race is more fair
                </h1>
                <h2>
                    This situation of equality vs. equity is seen often in our
                    everyday lives. An example of this was in the workplace as
                    shown by the BWDC website. The amount of black women in STEM
                    decreased while the amount of white men in STEM remained the
                    about the same. Now the cause of this isn't as simple as
                    black women not having an interest in STEM. There are
                    multiple circumstances and boundaries that have made it
                    diffuclt for black women and people of other minorities to
                    have an fair opportunity. Up until the 19th and 20th
                    centuries, women didn't even have access to education.
                    Without an education this heavily limited their
                    opportunities especially when it came to getting a job. This
                    obstacle created a generational problem for women. Compared
                    to men who were already had an access to education at an
                    early age, women were having to catch up on decades worth of
                    education. Even though nowadays women have access to
                    education, there are still stereotypes placed on them that
                    make it difficult for them to achieve their goals.
                </h2>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<ArticleText>
    <h2>
        This generational inequity and inequality is not only seen in gender,
        but race as well. In the United States, many minorites immigrated to the
        country. Often their opportunities for work are limited, especially if
        they don't have a college degree. For low income families, it is
        difficult for the children to afford higher education and if they don't
        have access to the education, it makes it difficult for them to get
        higher paying jobs.
    </h2>
    <img
        class="edu2"
        src="https://plus.unsplash.com/premium_photo-1663040081470-397e31e4b2a6?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
    />
</ArticleText>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img class="edu3-img" src="edu3.png" alt="Meeting in an office" />
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h1>Now what is affirmative action?</h1>
                <h2>
                    Universities have worked on plans to create more equity and
                    representation of minorities in the admissions system. An
                    example of this is affirmative action. It was first used in
                    the 2000s.
                </h2>

                <h2>
                    In multiple parts of the world, it is programs that focus on
                    improving the outcomes for ethnic, religious, or racial
                    minorities. However, affirmative action is highly
                    controversial. Even though it does bring in equity, some
                    feel that it is not fair for them to be judged based on
                    their race and the circumstances that were created by
                    generations before them.
                </h2>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<ArticleText>
    <h1>
        Black Women in STEM face systematic and generational barriers that make
        it challenging for them to work in STEM. There isn't a lack of drive or
        talent. These barriers aren't only seen in STEM and are seen across all
        races. In order to mitigate these barriers. We need action to be taken
        that creates equity, such as affirmative action, in order for us to
        achieve equailty.
    </h1>
    <img
        class="edu4"
        src="https://images.unsplash.com/photo-1542619147-5f08dc1ef985?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8ZXF1YWxpdHl8ZW58MHx8MHx8fDA%3D"
    />
</ArticleText>

<style>
    .edu1-img {
        width: 100%;
        margin: 0px auto;
    }
    .edu4 {
        width: 75%;
    }
</style>
