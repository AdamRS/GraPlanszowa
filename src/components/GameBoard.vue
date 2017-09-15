<template>
    <div class="container">
        <div class="info">
            <div class="player1Move" v-if="player1Round"> <button @click="player1Move">Player 1: wykonaj ruch</button></div>
            <div class="player2Move" v-if="player2Round"> <button @click="player2Move">Player 2: wykonaj ruch</button></div>
            {{ routeGame1.length}}   
        </div>
        <div class="gameBoard">
            <div class="P01"></div>
            <div class="P02"></div>
            <div class="P03"></div>
            <div class="P04"></div>
            <div class="P05"></div>
            <div class="P06"></div>
            <div class="P07"></div>
            <div class="P08"></div>
            <div class="P09"></div>
            <div class="P10"></div>
            <div class="P11"></div>
            <div class="P12"></div>
            <div class="P13"></div>
            <div class="P14"></div>
            <div class="P15"></div>
            <div class="P16"></div>
            <div class="P17"></div>
            <div class="P18"></div>
            <div class="P19"></div>
            <div class="P20"></div>
            <div class="P21"></div>
            <div class="P22"></div>
            <div class="P23"></div>
            <div class="P24"></div>
            <div class="P25"></div>
            <div class="P26"></div>
            <div class="P27"></div>
            <div class="P28"></div>
            <div class="P29"></div>
            <div class="P30"></div>
            <div class="P31"></div>
            <div class="P32"></div>
            <div class="P33"></div>
            <div class="P34"></div>
            <div class="P35"></div>
            <div class="P36"></div>
            <div class="P37"></div>
            <div class="P38"></div>
            <div class="P39"></div>
            <div class="P40"></div>
            <div class="P41"></div>
            <div class="P42"></div>
            <div class="P43"></div>
            <div class="P44"></div>
            <div class="P45"></div>
            <div class="P46"></div>
            <div class="P47"></div>
            <div class="P48"></div>
            <div class="P49"></div>
            <div class="P50"></div>
            <div class="P51"></div>
            <div class="P52"></div>
            <div class="P53"></div>
            <div class="P54"></div>
            <div class="P55"></div>
            <div class="P56"></div>
            <div class="P57"></div>
            <div class="P58"></div>
            <div class="P59"></div>
            <div class="P60"></div>
            <div class="P61"></div>
            <div class="P62"></div>
            <div class="P63"></div>
            <div class="P64"></div>
            <div class="player1" :style="{gridColumn: player1Column, gridRow: player1Row}"></div>
            <div class="player2" :style="{gridColumn: player2Column, gridRow: player2Row}"></div>
         </div>  
    </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
   
    data: function() {
        return {
            player1positon : 0,
            player1Round: false,
            player1Column: 1,
            player1Row: 1,
            player2positon : 0,
            player2Round: false,
            player2Column: 1,
            player2Row: 1,

            routeGame1 : [
                {
                    "fieldRow": "1",
                    "fieldColumn" : "1",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "2",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "3",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "4",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "5",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "6",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "7",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "8",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "9",
                },
                {
                    "fieldRow": "1",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "2",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "3",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "3",
                    "fieldColumn" : "9",
                },
                {
                    "fieldRow": "3",
                    "fieldColumn" : "8",
                },
                {
                    "fieldRow": "3",
                    "fieldColumn" : "7",
                },
                {
                    "fieldRow": "4",
                    "fieldColumn" : "7",
                },
                {
                    "fieldRow": "4",
                    "fieldColumn" : "6",
                },
                {
                    "fieldRow": "4",
                    "fieldColumn" : "5",
                },
                {
                    "fieldRow": "4",
                    "fieldColumn" : "4",
                },
                {
                    "fieldRow": "3",
                    "fieldColumn" : "4",
                },
                {
                    "fieldRow": "3",
                    "fieldColumn" : "3",
                },
                {
                    "fieldRow": "3",
                    "fieldColumn" : "2",
                },
                {
                    "fieldRow": "3",
                    "fieldColumn" : "1",
                },
                {
                    "fieldRow": "4",
                    "fieldColumn" : "1",
                },
                {
                    "fieldRow": "5",
                    "fieldColumn" : "1",
                },
                {
                    "fieldRow": "5",
                    "fieldColumn" : "2",
                },
                {
                    "fieldRow": "6",
                    "fieldColumn" : "2",
                },
                {
                    "fieldRow": "6",
                    "fieldColumn" : "3",
                },
                {
                    "fieldRow": "6",
                    "fieldColumn" : "4",
                },
                {
                    "fieldRow": "6",
                    "fieldColumn" : "5",
                },
                {
                    "fieldRow": "6",
                    "fieldColumn" : "6",
                },
                {
                    "fieldRow": "6",
                    "fieldColumn" : "7",
                },
                {
                    "fieldRow": "6",
                    "fieldColumn" : "8",
                },
                {
                    "fieldRow": "5",
                    "fieldColumn" : "8",
                },
                {
                    "fieldRow": "5",
                    "fieldColumn" : "9",
                },
                {
                    "fieldRow": "5",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "6",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "7",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "8",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "9",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "9",
                    "fieldColumn" : "10",
                },
                {
                    "fieldRow": "9",
                    "fieldColumn" : "9",
                },
                {
                    "fieldRow": "9",
                    "fieldColumn" : "8",
                },
                {
                    "fieldRow": "8",
                    "fieldColumn" : "8",
                },
                {
                    "fieldRow": "8",
                    "fieldColumn" : "7",
                },
                {
                    "fieldRow": "8",
                    "fieldColumn" : "6",
                },
                {
                    "fieldRow": "8",
                    "fieldColumn" : "5",
                },
                {
                    "fieldRow": "9",
                    "fieldColumn" : "5",
                },
                {
                    "fieldRow": "9",
                    "fieldColumn" : "4",
                },
                {
                    "fieldRow": "9",
                    "fieldColumn" : "3",
                },
                {
                    "fieldRow": "8",
                    "fieldColumn" : "3",
                },
                {
                    "fieldRow": "8",
                    "fieldColumn" : "2",
                },
                {
                    "fieldRow": "8",
                    "fieldColumn" : "1",
                },
                {
                    "fieldRow": "9",
                    "fieldColumn" : "1",
                },
                {
                    "fieldRow": "10",
                    "fieldColumn" : "1",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "1",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "2",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "3",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "4",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "5",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "6",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "7",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "8",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "9",
                },
                {
                    "fieldRow": "11",
                    "fieldColumn" : "10",
                },

            ],
            drawnNumber: Number,
            throwCounter: Number,
            throwCounter2: Number,
            gameIsRunning : false,

        }
    },
     props: {

    },
    created: function() {
        eventBus.$on('drawnNumberChange', (number) => {
        this.drawnNumber = number;
        });
        eventBus.$on('counterChange', (number2) => {
            this.throwCounter = number2;
        });
         eventBus.$on('counterChange2', (number3) => {
            this.throwCounter2 = number3;
        });
    },
    methods: {
        startGame: function() {
            this.player1positon =0,
            this.player1Round= false,
            this.player1Column= 1,
            this.player1Row= 1,
            this.player2positon = 0,
            this.player2Round= false,
            this.player2Column= 1,
            this.player2Row= 1,
            this.gameIsRunning = true;

            eventBus.$emit('gameRunning', this.gameIsRunning);

        },
        player1Move: function(){
            this.player1positon+= this.drawnNumber;
            console.log(this.player1positon) ;
            if (this.player1positon > this.routeGame1.length-1) {
                this.player1positon = this.routeGame1.length -1 ;
                console.log(this.player1positon) ;
            }
            
            this.player1Column = this.routeGame1[this.player1positon].fieldColumn;
            this.player1Row = this.routeGame1[this.player1positon].fieldRow;
            this.player1Round = false;
            this.checkWin();
        },
        player2Move: function(){
            this.player2positon+= this.drawnNumber;
            if (this.player2positon > this.routeGame1.length-1) {
                this.player2positon = this.routeGame1.length -1 ;
                console.log(this.player1positon) ;
            }
            this.player2Column = this.routeGame1[this.player2positon].fieldColumn;
            this.player2Row = this.routeGame1[this.player2positon].fieldRow;
            this.player2Round = false;
            this.checkWin();

        },
        checkWin: function() {
            if (this.player1positon == 64) {
                if (confirm('Player1 wygrał. Chcecie zagrać jeszcze raz??')){
                    this.startGame();
                    return;
                }else {
                    this.gameIsRunning = false;
                    eventBus.$emit('gameRunning', this.gameIsRunning);
                }
            }
            if (this.player2positon == 64) {
                if (confirm('Player2 wygrał. Chcecie zagrać jeszcze raz??')){
                    this.startGame();
                    return;
                }else {
                    this.gameIsRunning = false;
                    eventBus.$emit('gameRunning', this.gameIsRunning);
                }
            }
        }
    },
    watch: {
        throwCounter: function() {
            if (this.throwCounter % 2 ==0) {
                this.player2Round = !this.player2Round;
            }else {
                this.player1Round = !this.player1Round;
            }
        },
         throwCounter2: function() {
            if (this.throwCounter2 % 2 ==0) {
                this.player1Round = false;
            }else {
                this.player2Round = false;
            }
        }    
    }
    
}
</script>

<style scoped>
.player2Move {
text-align: right;
}

.container {
    grid-template-columns:  1fr;
    grid-template-rows: 1fr 1fr;
    grid-gap: 3px;
    height: 627px;

}

.info {
width: 100%;
height: 100px;
background-color: cadetblue;

}

.player2 {
    height: 20px;
    width: 20px;
    background-color: white;
    grid-column: 1;
    grid-row: 1;   
    align-self: end;
    justify-self: center;
}

.player1 {
    height: 20px;
    width: 20px;
    background-color: red;
    grid-column: 1;
    grid-row: 1;   
    align-self: start;
    justify-self: center;
}

.gameBoard>div {
    border-radius: 25%;
}

.gameBoard {
    width: 527px;
    height: 527px;
    display: grid;
    grid-template-columns: repeat(10, 50px);
    grid-template-rows: repeat(11, 50px);
    grid-gap: 3px;
    margin: 0 auto;
}

.P01{
    grid-column: 1;
    grid-row: 1;
    background-color: blue;
}
.P02{
    grid-column: 2;
    grid-row: 1;
    background-color: blue;
}
.P03{
    grid-column: 3;
    grid-row: 1;
    background-color: blue;
}
.P04{
    grid-column: 4;
    grid-row: 1;
    background-color: blue;
}
.P05{
    grid-column: 5;
    grid-row: 1;
    background-color: blue;
}
.P06{
    grid-column: 6;
    grid-row: 1;
    background-color: blue;
}
.P07{
    grid-column: 7;
    grid-row: 1;
    background-color: blue;
}
.P08{
    grid-column: 8;
    grid-row: 1;
    background-color: blue;
}
.P09{
    grid-column: 9;
    grid-row: 1;
    background-color: blue;
}
.P10{
    grid-column: 10;
    grid-row: 1;
    background-color: blue;
}
.P11{
    grid-column: 10;
    grid-row: 2;
    background-color: blue;
}
.P12{
    grid-column: 10;
    grid-row: 3;
    background-color: blue;
}
.P13{
    grid-column: 9;
    grid-row: 3;
    background-color: blue;
}
.P14{
    grid-column: 8;
    grid-row: 3;
    background-color: blue;
}
.P15{
    grid-column: 7;
    grid-row: 3;
    background-color: blue;
}
.P16{
    grid-column: 7;
    grid-row: 4;
    background-color: blue;
}
.P17{
    grid-column: 6;
    grid-row: 4;
    background-color: blue;
}
.P18{
    grid-column: 5;
    grid-row: 4;
    background-color: blue;
}
.P19{
    grid-column: 4;
    grid-row: 4;
    background-color: blue;
}
.P20{
    grid-column: 4;
    grid-row: 3;
    background-color: blue;
}
.P21{
    grid-column: 3;
    grid-row: 3;
    background-color: blue;
}
.P22{
    grid-column: 2;
    grid-row: 3;
    background-color: blue;
}
.P23{
    grid-column: 1;
    grid-row: 3;
    background-color: blue;
}
.P24{
    grid-column: 1;
    grid-row: 4;
    background-color: blue;
}
.P25{
    grid-column: 1;
    grid-row: 5;
    background-color: blue;
}
.P26{
    grid-column: 2;
    grid-row: 5;
    background-color: blue;
}
.P27{
    grid-column: 2;
    grid-row: 6;
    background-color: blue;
}
.P28{
    grid-column: 3;
    grid-row: 6;
    background-color: blue;
}
.P29{
    grid-column:4;
    grid-row: 6;
    background-color: blue;
}
.P30{
    grid-column: 5;
    grid-row: 6;
    background-color: blue;
}
.P31{
    grid-column: 6;
    grid-row: 6;
    background-color: blue;
}
.P32{
    grid-column: 7;
    grid-row: 6;
    background-color: blue;
}
.P33{
    grid-column: 8;
    grid-row: 6;
    background-color: blue;
}
.P34{
    grid-column: 8;
    grid-row: 5;
    background-color: blue;
}
.P35{
    grid-column: 9;
    grid-row: 5;
    background-color: blue;
}
.P36{
    grid-column: 10;
    grid-row: 5;
    background-color: blue;
}
.P37{
    grid-column: 10;
    grid-row: 6;
    background-color: blue;
}
.P38{
    grid-column: 10;
    grid-row: 7;
    background-color: blue;
}
.P39{
    grid-column: 10;
    grid-row: 8;
    background-color: blue;
}
.P40{
    grid-column: 10;
    grid-row: 9;
    background-color: blue;
}
.P41{
    grid-column: 9;
    grid-row: 9;
    background-color: blue;
}
.P42{
    grid-column: 8;
    grid-row: 9;
    background-color: blue;
}
.P43{
    grid-column: 8;
    grid-row: 8;
    background-color: blue;
}
.P44{
    grid-column: 7;
    grid-row: 8;
    background-color: blue;
}
.P45{
    grid-column: 6;
    grid-row: 8;
    background-color: blue;
}
.P46{
    grid-column: 5;
    grid-row: 8;
    background-color: blue;
}
.P47{
    grid-column: 5;
    grid-row: 9;
    background-color: blue;
}
.P48{
    grid-column: 4;
    grid-row: 9;
    background-color: blue;
}
.P49{
    grid-column: 3;
    grid-row: 9;
    background-color: blue;
}
.P50{
    grid-column: 3;
    grid-row: 8;
    background-color: blue;
}
.P51{
    grid-column: 2;
    grid-row: 8;
    background-color: blue;
}
.P52{
    grid-column: 1;
    grid-row: 8;
    background-color: blue;
}
.P53{
    grid-column: 1;
    grid-row: 9;
    background-color: blue;
}
.P54{
    grid-column: 1;
    grid-row: 10;
    background-color: blue;
}
.P55{
    grid-column: 1;
    grid-row: 11;
    background-color: blue;
}
.P56{
    grid-column: 2;
    grid-row: 11;
    background-color: blue;
}
.P57{
    grid-column: 3;
    grid-row: 11;
    background-color: blue;
}
.P58{
    grid-column: 4;
    grid-row: 11;
    background-color: blue;
}
.P59{
    grid-column: 5;
    grid-row: 11;
    background-color: blue;
}
.P60{
    grid-column: 6;
    grid-row: 11;
    background-color: blue;
}
.P61{
    grid-column: 7;
    grid-row: 11;
    background-color: blue;
}
.P62{
    grid-column: 8;
    grid-row: 11;
    background-color: blue;
}
.P63{
    grid-column: 9;
    grid-row: 11;
    background-color: blue;
}
.P64{
    grid-column: 10;
    grid-row: 11;
    background-color: blue;
}
</style>
