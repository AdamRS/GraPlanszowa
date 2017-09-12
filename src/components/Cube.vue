<template>
<div>
    <div class="cube" v-if="drawnNumber == 1">
        <div class="cubeArea4"></div>
    </div>
        <div class="cube" v-if="drawnNumber == 2">
        <div class="cubeArea1"></div>
        <div class="cubeArea7"></div>
    </div>
        <div class="cube" v-if="drawnNumber == 3">
        <div class="cubeArea1"></div>
        <div class="cubeArea4"></div>
        <div class="cubeArea7"></div>
    </div>
        <div class="cube" v-if="drawnNumber == 4">
        <div class="cubeArea1"></div>
        <div class="cubeArea2"></div>
        <div class="cubeArea6"></div>
        <div class="cubeArea7"></div>
    </div>
        <div class="cube" v-if="drawnNumber == 5">
        <div class="cubeArea1"></div>
        <div class="cubeArea2"></div>
        <div class="cubeArea4"></div>
        <div class="cubeArea6"></div>
        <div class="cubeArea7"></div>
    </div>
        <div class="cube" v-if="drawnNumber == 6">
        <div class="cubeArea1"></div>
        <div class="cubeArea2"></div>
        <div class="cubeArea3"></div>
        <div class="cubeArea5"></div>
        <div class="cubeArea6"></div>
        <div class="cubeArea7"></div>
    </div>
    <button @click="throwCube6">Wylosuj </button>
    <div v-if="drawnNumber != 0 ">Wylosowano: {{ drawnNumber }}</div>
</div>

  
</template>

<script>
export default {
    data: function() {
        return { 
            drawnNumber: 0 
        }
    },
    methods: {
        throwCube : function() {
            for (var i = 1; i <= 6; i++) {
            setTimeout(function(x) { return function() { this.drawnNumber = x }; }(i).bind(this), 100*i);
            }
        },
        throwCube6: function() {
            for (var j = 1; j <= 6; j++) {
            setTimeout(function(x) { return function() { this.throwCube() }; }(j).bind(this), 600*j);
            }
            setTimeout(function(){this.drawnNumber = Math.max(Math.floor(Math.random() * 6) +1, 1)}.bind(this),4300);
        }
        
    }


  
}
</script>

<style>
.cube {
    display: grid;
    grid-template-columns: repeat(3, 50px);
    grid-template-rows: repeat(3, 50px);
    grid-gap: 2px;

}
.cube>div {
    background-color: red;
    border-radius: 35%;
}

.cubeArea1 {
    grid-column: 1;
    grid-row: 1
}

.cubeArea2 {
    grid-column: 3;
    grid-row: 1
}

.cubeArea3 {
    grid-column: 1;
    grid-row: 2
}

.cubeArea4 {
    grid-column: 2;
    grid-row: 2
}

.cubeArea5 {
    grid-column: 3;
    grid-row: 2
}

.cubeArea6 {
    grid-column: 1;
    grid-row: 3
}

.cubeArea7 {
    grid-column: 3;
    grid-row: 3
}
</style>


