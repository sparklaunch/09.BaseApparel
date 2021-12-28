<div id="form">
    <form>
        <input type="email" placeholder="Email Address" required />
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
    }
    #form > form > input {
        outline: none;
        border: none;
        padding: 15px 30px;
        background-color: transparent;
        font-size: 20px;
        /* Worth noting that all input elements have default min-width properties */
        min-width: 0;
        flex: 1 1 100%;
        text-overflow: ellipsis;
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
    }
</style>
