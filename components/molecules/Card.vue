<template>
    <article>
        <NuxtLink to="/" class="cardLink">
            <img src="https://loremflickr.com/320/240?random=1"/>
            <h3>Fils de Pute</h3>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Id quas ea tenetur tempore qui dolores? Rerum consequuntur corporis inventore, non dolores officiis dolorem unde ipsam debitis quasi. Libero quo illo commodi dicta, error harum blanditiis maxime ab consectetur, tempora nisi beatae temporibus possimus assumenda quis iste sit, et consequuntur autem?</p>
        </NuxtLink>
    </article>
</template>

<style scoped>
    
.cardLink {
    padding: 5rem 1.5rem 3rem 1.5rem;
    display: grid;
    gap: 1rem;
    width: fit-content;
    background-color: var(--secondary-color);
    display: grid;
    place-items: center;
    text-align: center;
    box-shadow: 0 0 10px rgba(0,0,0, 0.15);
    transition: transform .3s ease-in-out, box-shadow .4s;
}
.cardLink:is(:hover, :focus) {
    transform: scale(1.05);
    box-shadow: 0 0 10px rgba(0,0,0, 0.25);
}

.cardLink img{
    margin-bottom: 1.5rem;
    width: 35%;
}
</style>