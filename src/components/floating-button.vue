<script>
export default {
    name: 'Floating-Button',
}
</script>

<template>
    <div class="floating-button floating-donate">
        <div class="floating-donate-inner">
            <p>donate</p>
        </div>
    </div>

    <div class="floating-button floating-webflow">
        <img src="../assets/images/webflow-logo.svg" alt="">
        <img src="../assets/images/webflow-text.svg" alt="">
    </div>
</template>

<style>
.floating-button {
    position: fixed;
    cursor: pointer;
    z-index: 999;
    transition: background-color 0.3s;
}

.floating-donate-inner {
    display: flex;
    justify-content: center;
    width: 10vw;
    top: 2vw;
    right: 2vw;
    padding: 0.5vw 1vw;
    color: black;
    font-size: 2vw;
    border-style: solid;
    border-color: black;
    border-width: 3.5px;
    background-color: transparent;
    transition: ease 0.3s;
}

.floating-donate {
    top: 2vw;
    right: 2vw;
    width: auto;
    background-color: white;
}

.floating-webflow {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.3vw;
    bottom: 0.5vw;
    right: 0.5vw;
    padding: 0.4vw 0.5vw;
    background-color: white;
    box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.3);
    border-radius: 0.3vw;
    color: black;
    font-size: 2vw;
}

.floating-donate:hover .floating-donate-inner {
    transform: translate(0.5vw, -0.5vw);
    transition: ease 0.3s;
}

@media only screen and (max-width: 900px) {

    .floating-donate {
        top: 5vw;
        right: 5vw;
        font-size: 2.5vw;
    }

    .floating-donate-inner {
        width: 11vw;
        padding: 1vw 1.5vw;
        font-size: 2.5vw;
    }

    .floating-webflow {
        gap: 0.3vw;
        bottom: 1vw;
        right: 1vw;
        padding: 1vw 1.2vw;
        background-color: white;
        box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.3);
        border-radius: 0.3vw;
        color: black;
        font-size: 2vw;
    }

    .floating-donate:hover .floating-donate-inner {
        transform: translate(0.8vw, -0.8vw);
    }
}

@media only screen and (max-width: 480px) {

    .floating-donate {
        top: 7vw;
        right: 7vw;
        font-size: 4vw;
    }

    .floating-donate-inner {
        width: 18vw;
        padding: 1.5vw 2vw;
        font-size: 4vw;
    }

    .floating-webflow {
        gap: 0.3vw;
        bottom: 2.5vw;
        right: 2.5vw;
        padding: 1.4vw 1.8vw;
        background-color: white;
        box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.3);
        border-radius: 0.3vw;
        color: black;
        font-size: 2vw;
    }

    .floating-donate:hover .floating-donate-inner {
        transform: translate(1.5vw, -1.5vw);
    }

}
</style>