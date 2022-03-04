<template>
    <section>
        <form autocomplete="off">

            <input id="nextStep" type="checkbox">
            <input id="prevStep" type="checkbox">

            <label for="prevStep" class="chevron">
                <div role="button">
                    <span class="material-icons">chevron_left</span>
                </div>
            </label>

            <!-- Username -->
            <div id="step_user">
                <label>Username</label>
                <input type="text" name="username">
            </div><!-- /Username -->
            
            <!-- Password -->
            <div id="step_pass">
                <label>Password</label>
                <input type="password" name="password">
            </div><!-- /Password -->

            <label for="nextStep" class="chevron">
                <div role="button">
                    <span class="material-icons">chevron_right</span>
                </div>
            </label>

        </form>
    </section>
</template>

<script setup lang="ts">

</script>

<style scoped>
    form{
        display: grid;
        grid-template-columns: 0.5fr 2fr 0.5fr;
        grid-template-rows: 1fr;
        grid-template-areas:
            "arrow-left input arrow-right";
        justify-items: center;
        align-items: center;

        width: 50vw;
    }

    .chevron div span{
        font-size: 3rem;
    }
    #prevStep{
        grid-area: arrow-left;
    }
    #nextStep{
        grid-area: arrow-right;
    }

/* Hide Checkboxes */
    input[type=checkbox] {
        position: absolute;
        opacity: 0;
    }

    #step_user, #step_pass{
        display: flex;
        /*justify-content: space-around;*/
        justify-content: space-around;
        align-items: center;
        flex-direction: column;
        
        height: 15vh;

        font-size: 1.5rem;
        opacity: 1;
        /*transition: opacity 1s ease-in-out;*/
        grid-area: input;
    }

    label{
        /*padding: 0.5rem;*/
    }

    input[type="text"], input[type="password"]{
        padding: 0.5rem;

        width: 30vw;
        height: 5vh;
        font-size: 1.5rem;

        border: none;
        border-bottom: 1px solid cyan;
        background: none;
        outline: none;
        color: cyan;
    }

/* Hidden Parts */
    #step_pass{
        opacity: 0;
        height: 0;
        overflow: hidden;
    }

/* Hide Step 1 */
    #nextStep:checked ~ #step_pass {
        opacity: 1;
        height: 15vh;
    }

    #nextStep:checked ~ #step_user {
        opacity: 0;
        height: 0;
        display: none;
    }

/* Hide Step 1 */
    #prevStep:checked ~ #step_user {
        opacity: 1;
        height: 15vh;
    }

    #prevStep:checked ~ #step_pass {
        opacity: 0;
        height: 0;
        display: none;
    }
</style>