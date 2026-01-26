<template>
    <div class="flex justify-center gap-18 p-6" style="flex-wrap: nowrap;">
        <div
            v-for="(card, index) in cards"
            :key="index"
            :class="['card-float', card.animationClass]"
            class="md:w-32 md:h-40 w-18 h-28 rounded-2xl overflow-visible relative transform transition-all duration-500 hover:scale-105 hover:z-50"
            :style="{
            backgroundColor: card.bg,
            marginLeft: index === 0 ? '0' : '-80px', /* negativo para solaparlas */
            zIndex: index + 1 /* para que las tarjetas laterales estén debajo */
            }"
        >
            <div class="absolute inset-0 z-0 pt-8">
                <img
                    :src="card.img"
                    alt="Card Illustration"
                    class="w-[100%] h-[100%] object-cover object-center pointer-events-none transition-transform duration-500 hover:scale-105"
                />
            </div>
        </div>
    </div>

</template>

<script setup>
    const cards = [
        {
            img: 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Laravel.svg/1200px-Laravel.svg.png',
            bg: '#fff',
            animationClass: 'card-float-right'
        },
        {
            img: 'https://pngimg.com/d/php_PNG30.png',
            bg: '#fff',
            animationClass: 'card-float-down'
        },
        {
            img: 'https://miro.medium.com/1*NJSv6DGoKTloI8d8im98zg.png',
            bg: '#fff',
            animationClass: 'card-float-left'
        },
        {
            img: 'https://nuxt.com/assets/design-kit/icon-green.png',
            bg: '#fff',
            animationClass: 'card-float-down'
        },
        {
            img: 'https://cdn-icons-png.flaticon.com/512/919/919828.png',
            bg: '#fff',
            animationClass: 'card-float-UpRight'
        },
        {
            img: 'https://img.icons8.com/plasticine/512/tailwind_css.png',
            bg: '#fff',
            animationClass: 'card-float-left'
        }
    ]
</script>

<style scoped>

    .card-float {
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        animation: entryBounce 0.8s ease forwards;
        will-change: transform;
        cursor: pointer;
        overflow: visible;
    }

    .card-float-right {
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        animation: floatRight 2s ease infinite;
        will-change: transform;
        cursor: pointer;
        overflow: visible;
    }

    .card-float-UpRight {
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        animation: floatUpRight 2s ease infinite;
        will-change: transform;
        cursor: pointer;
        overflow: visible;
    }

    .card-float-left {
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        animation: floatLeft 2s ease infinite;
        will-change: transform;
        cursor: pointer;
        overflow: visible;
    }

    .card-float-down {
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        animation: floatDown 2s ease infinite;
        will-change: transform;
        cursor: pointer;
        overflow: visible;
    }

    .card-float:hover {
        animation: floatHover 3s ease-in-out infinite;
    }

@keyframes floatHover {
  0%, 100% {
    transform: translateY(0) rotate(0);
  }
  50% {
    transform: translateY(-10px) rotate(3deg);
  }
}

/* Flotar derecha */
@keyframes floatRight {
  0%, 100% {
    transform: translateX(0) rotate(0);
  }
  50% {
    transform: translateX(10px) rotate(3deg);
  }
}

/* Flotar diagonal arriba-derecha */
@keyframes floatUpRight {
  0%, 100% {
    transform: translate(0, 0) rotate(0);
  }
  50% {
    transform: translate(10px, -10px) rotate(3deg);
  }
}

/* Flotar izquierda */
@keyframes floatLeft {
  0%, 100% {
    transform: translateX(0) rotate(0);
  }
  50% {
    transform: translateX(-10px) rotate(-3deg);
  }
}

/* Flotar abajo */
@keyframes floatDown {
  0%, 100% {
    transform: translateY(0) rotate(0);
  }
  50% {
    transform: translateY(10px) rotate(-3deg);
  }
}


@keyframes entryBounce {
  0% {
    opacity: 0;
    transform: translateY(30px) scale(0.95);
  }
  100% {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}
</style>
