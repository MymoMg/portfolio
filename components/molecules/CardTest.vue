<template>
    <article>
        <NuxtLink to="/" class="cardLink">
            <div>
                <img src="https://loremflickr.com/320/240?random=1"/>
                <h3>Fils de Pute</h3>
            </div>
        </NuxtLink>
    </article>
</template>

<style scoped>
    
@property --gradient-angle {
  syntax: "<angle>";
  initial-value: 0deg;
  inherits: false;
}


.cardLink {
    --clr-1: #052b2f;
    --clr-2: #073438;
    --clr-3: #0e4b50;
    --clr-4: #2d8f85;
    --clr-5: #637c54;
    --conic-gradients: conic-gradient(from var(--gradient-angle),
        var(--clr-3),
        var(--clr-4),
        var(--clr-5),
        var(--clr-4),
        var(--clr-3)
    );

    display: grid;
    position: relative;
    background-color: var(--secondary-color);
    width: 50%;
    margin: 0 auto;
    padding: 1rem;
    border-radius: 10px;
    transform: scale(1);
    box-shadow: 0 0 10px rgba(0,0,0, 0.15);
    transition: transform .3s ease-in-out, box-shadow .4s;
}


.cardLink img{
    transition: transform .5s;
    margin-bottom: 1.5rem;
    width: 55%;
}
.cardLink > div {
    display: grid;
    place-items: center;
    position: relative;
    padding: 3.5rem 1rem;     
    background-color: inherit;
    border-radius: inherit;
}
.cardLink > div::before,
.cardLink > div::after{
  content: "";
  position: absolute;
  inset: -1px;
  z-index: -1;
  background: var(--conic-gradients);
  border-radius: inherit;
  animation: rotation 2s linear infinite;
}

.cardLink > div::after {
  filter: blur(2px);
}


.cardLink:is(:hover, :focus) {
    transform: scale(1.05);
    box-shadow: 0 0 10px rgba(0,0,0, 0.20);
}
.cardLink:is(:hover, :focus) img {
    transform: scaleY(1.05);
}

@keyframes rotation {
  0% {
    --gradient-angle: 0deg;
  }
  100% {
    --gradient-angle: 360deg;
  }
}

</style>