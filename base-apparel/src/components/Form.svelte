<script lang="ts">
    import { slide } from "svelte/transition";
    let emailInput: HTMLInputElement;
    let isEmailEmpty: boolean = false;
    let isEmailValid: boolean = true;
    $: isInvalid = isEmailEmpty || !isEmailValid;
    const emailRegExp: RegExp = new RegExp(
        /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
    );
    const submitHandler = () => {
        const email: string = emailInput.value;
        if (email === "") {
            isEmailEmpty = true;
        } else if (!emailRegExp.test(email)) {
            isEmailValid = false;
            isEmailEmpty = false;
        } else {
            isEmailEmpty = false;
            isEmailValid = true;
        }
    };
</script>

<div id="form">
    <form
        on:submit|preventDefault={submitHandler}
        novalidate
        class:invalid={isInvalid}
    >
        <input
            type="email"
            placeholder="Email Address"
            bind:this={emailInput}
            required
        />
        {#if isEmailEmpty}
            <p transition:slide class="warning">Email cannot be empty</p>
        {:else if !isEmailValid}
            <p transition:slide class="warning">Please provide a valid email</p>
        {/if}
        {#if isInvalid}
            <img class="icon-error" src="/assets/icon-error.svg" alt="Error" />
        {/if}
        <button type="submit">
            <img src="/assets/icon-arrow.svg" alt="Arrow" />
        </button>
    </form>
</div>

<style>
    #form > form {
        display: flex;
        align-items: stretch;
        border: 1px solid rgb(223, 192, 190);
        border-radius: 30px;
        transition: border 0.3s;
        position: relative;
    }
    .invalid {
        border: 1px solid rgb(230, 110, 105) !important;
    }
    #form > form > input {
        outline: none;
        border: none;
        padding: 20px 30px 15px 30px;
        background-color: transparent;
        font-size: 20px;
        /* Worth noting that all input elements have default min-width properties */
        min-width: 0;
        flex: 1 1 100%;
        text-overflow: ellipsis;
        color: rgb(93, 85, 85);
    }
    #form > form > input::placeholder {
        color: rgba(223, 192, 190, 0.8);
    }
    #form > form > button {
        border: none;
        background: linear-gradient(
            to right,
            rgb(237, 186, 184),
            rgb(225, 150, 150)
        );
        flex: 0 0 80px;
        border-radius: 30px;
        cursor: pointer;
        box-shadow: 0px 10px 15px -3px rgba(225, 150, 150, 0.5);
        transition: filter 0.3s;
    }
    #form > form > button:hover {
        filter: brightness(1.1);
    }
    .warning {
        color: rgb(230, 110, 105);
        font-size: 14px;
        position: absolute;
        bottom: -25px;
        left: 30px;
    }
    .icon-error {
        align-self: center;
        margin: 0 20px;
    }
</style>
