<template>
    <div class="chess-board">
      <div 
        v-for="row in 8" 
        :key="row" 
        class="board-row"
      >
        <div 
          v-for="col in 8" 
          :key="`${row}-${col}`" 
          :class="['board-square', getSquareColor(row, col)]"
        >
          <span class="square-notation">{{ getSquareNotation(row, col) }}</span>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  const files = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']
  
  const getSquareColor = (row, col) => {
    return (row + col) % 2 === 0 ? 'light' : 'dark'
  }
  
  const getSquareNotation = (row, col) => {
    return `${files[col - 1]}${9 - row}`
  }
  </script>
  
  <style lang="scss" scoped>
  .chess-board {
    width: var(--board-size);
    height: var(--board-size);
    display: grid;
    grid-template-rows: repeat(8, 1fr);
    border: 4px solid var(--primary-color);
    background: var(--primary-color);
    gap: 1px;
    padding: 1px;
    
    .board-row {
      display: grid;
      grid-template-columns: repeat(8, 1fr);
      gap: 1px;
    }
    
    .board-square {
      aspect-ratio: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      
      &.light {
        background-color: var(--square-light);
      }
      
      &.dark {
        background-color: var(--square-dark);
      }
  
      .square-notation {
        font-size: 0.8rem;
        opacity: 0.5;
        position: absolute;
        bottom: 2px;
        right: 2px;
      }
    }
  }
  </style>