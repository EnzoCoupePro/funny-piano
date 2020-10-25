<template>
    <div class="note">
            <p id="C">DO</p>
            <p id="D">RE</p>
            <p id="E">MI</p>
            <p id="F">FA</p>
            <p id="G">SOL</p>
            <p id="A">LA</p>
            <p id="B">SI</p>
        </div>
</template>

<style lang="postcss" scoped>
.note {
    width: 500px;
    height: 22px;
    display: flex;
    justify-content: center;
    margin: 48px auto;
    
}

.note p {
    margin: 0 15px;
    flex: 1;
    
    
}
@media (max-width:650px){
    .note{
        visibility: hidden;
    }
}
</style>