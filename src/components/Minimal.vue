<template>
    <div class="login">
        <div class="form">
            <h2>Login</h2>

            <div class="field">
                <input type="text" name="user">
                <label>Username</label>
            </div>

            <div class="field">
                <input type="password" name="pass">
                <label>Password</label>
            </div>

            <button>Submit</button>
        </div>

        <div class="switch">
            <button>Foo</button>
            <button>Bar</button>
        </div>
    </div>
</template>

<script lang="ts">

</script>

<style scoped>
    .login{
        position: absolute;

        width: 30vw;
        height: 30vw;

        display: grid;
        grid-gap: 2vh;
        grid-template-rows: 5fr 1fr;

        font-size: 1vw;
        background: #101227;
        border-radius: 15px 15px 0 0;
    }

    .form{
        width: 100%;

        display: grid;
        grid-gap: 2vh;
        grid-template-columns: 80%;
        grid-template-rows: repeat(4, 1fr);
        justify-content: center;
        align-items: center;

        /*padding: 2vw;*/
    }

    .form h2{
        width: 100%;
        text-align: center;
    }

    .field{
        position: relative;
        display: flex;
        justify-content: left;
        align-items: baseline;
    }

    .field input{
        width: 66%;
        height: 3vh;

        color: white;
        font-size: 1vw;

        border: none;
        border-bottom: 1px solid white;
        background: none;
        outline: none;
    }

    .field label{
        width: 66%;
        height: 3vh;

        position: absolute;
        top: 0;
        left: 0;

        font-size: 1vw;
        z-index: 10;
        pointer-events: none;
        transition: .5s;
    }

    .field input:focus ~ label {
        top: -66%;
        left: 0;
        color: #03e9f4;
        font-size: 0.6vw;
    }

    .form button{
        width: 66%;
        height: 50%;
        margin: auto;
    }

    .switch button{
        width: 50%;
        height: 100%;
        border-radius: 0;
        border: none;
    }

/*        
    -blue: #00B6D8;
    -dark: #272833;

    -graph-bg: #f8f8f8;
    -bg: #fff;
    -light-text: #fff;
    -dark-text: #000;
*/
</style>
