<template>
  <span 
    class="type-badge"
    :style="{ background: getTypeColor(type).bg, color: getTypeColor(type).text }"
  >
    {{ getTypeName(type) }}
  </span>
</template>

<script setup>
// Props
const props = defineProps({
  type: {
    type: String,
    required: true
  }
})

// Methods
const getTypeColor = (type) => {
  const typeColors = {
    normal: { bg: 'linear-gradient(135deg, #A8A878 0%, #969666 100%)', text: '#ffffff' },
    fire: { bg: 'linear-gradient(135deg, #F08030 0%, #e67329 100%)', text: '#ffffff' },
    water: { bg: 'linear-gradient(135deg, #6890F0 0%, #5a7fd8 100%)', text: '#ffffff' },
    electric: { bg: 'linear-gradient(135deg, #F8D030 0%, #f4c82e 100%)', text: '#2d3748' },
    grass: { bg: 'linear-gradient(135deg, #78C850 0%, #6bb847 100%)', text: '#ffffff' },
    ice: { bg: 'linear-gradient(135deg, #98D8D8 0%, #8ac8c8 100%)', text: '#2d3748' },
    fighting: { bg: 'linear-gradient(135deg, #C03028 0%, #a82923 100%)', text: '#ffffff' },
    poison: { bg: 'linear-gradient(135deg, #A040A0 0%, #8a378a 100%)', text: '#ffffff' },
    ground: { bg: 'linear-gradient(135deg, #E0C068 0%, #d4b45e 100%)', text: '#2d3748' },
    flying: { bg: 'linear-gradient(135deg, #A890F0 0%, #967fd8 100%)', text: '#ffffff' },
    psychic: { bg: 'linear-gradient(135deg, #F85888 0%, #e64d7a 100%)', text: '#ffffff' },
    bug: { bg: 'linear-gradient(135deg, #A8B820 0%, #96a61c 100%)', text: '#ffffff' },
    rock: { bg: 'linear-gradient(135deg, #B8A038 0%, #a69032 100%)', text: '#ffffff' },
    ghost: { bg: 'linear-gradient(135deg, #705898 0%, #624d82 100%)', text: '#ffffff' },
    dragon: { bg: 'linear-gradient(135deg, #7038F8 0%, #622fd8 100%)', text: '#ffffff' },
    dark: { bg: 'linear-gradient(135deg, #705848 0%, #624d3e 100%)', text: '#ffffff' },
    steel: { bg: 'linear-gradient(135deg, #B8B8D0 0%, #a6a6be 100%)', text: '#2d3748' },
    fairy: { bg: 'linear-gradient(135deg, #EE99AC 0%, #d8889a 100%)', text: '#ffffff' }
  }
  return typeColors[type] || { bg: 'linear-gradient(135deg, #A8A878 0%, #969666 100%)', text: '#ffffff' }
}

const getTypeName = (type) => {
  const typeNames = {
    normal: 'Normal',
    fire: 'Fuego',
    water: 'Agua',
    electric: 'Eléctrico',
    grass: 'Planta',
    ice: 'Hielo',
    fighting: 'Lucha',
    poison: 'Veneno',
    ground: 'Tierra',
    flying: 'Volador',
    psychic: 'Psíquico',
    bug: 'Bicho',
    rock: 'Roca',
    ghost: 'Fantasma',
    dragon: 'Dragón',
    dark: 'Siniestro',
    steel: 'Acero',
    fairy: 'Hada'
  }
  return typeNames[type] || type
}
</script>

<style scoped>
.type-badge {
  padding: 6px 12px;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 500;
  text-transform: capitalize;
  transition: all 0.3s ease;
  cursor: pointer;
  position: relative;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.type-badge:hover {
  transform: translateY(-2px) scale(1.05);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  filter: brightness(1.1);
}

.type-badge::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s ease;
}

.type-badge:hover::before {
  left: 100%;
}
</style> 