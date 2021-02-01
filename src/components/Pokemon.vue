<template>
    <div>
        <p>ピカチュウ</p>
        <div v-text="moveBtnMsg" v-on:click="showMoves"></div>
        <div v-text="typeBtnMsg" v-on:click="showTypes"></div>
        <div>
            <div v-html="typeTable"></div>
        </div>
        <div>
            <div v-html="moveTable"></div>
        </div>
    </div>
</template>

<script>
import PikachuObj from './pokemon/Pikachu.vue'

let PokemonObj = {
    name : 'Pokemon',
    data : function() {
        return {
            Pikachu : PikachuObj,
            moveBtnMsg  : '技を表示',
            moveTable : '',
            typeBtnMsg : 'タイプを表示',
            typeTable : '',
        }
    },
    methods : {
        showMoves : function() {
            if (this.moveBtnMsg === '技を非表示') {
                this.moveBtnMsg    = '技を表示';
                this.moveTable = '';
                return;
            }

            this.moveBtnMsg = '技を非表示';
            let tableHeader = '<tr><th>レベル</th><th>覚える技</th></tr>';

            let initMovesTr = '';
            for (let i in this.Pikachu.initMoves) {
                initMovesTr += `<tr><td>基本</td><td>${this.Pikachu.initMoves[i]}</td></tr>`;
            }

            let levelUpMovesTr = '';
            for (let i in this.Pikachu.levelUpMoves) {
                levelUpMovesTr += `<tr><td>レベル${i}</td><td>${this.Pikachu.levelUpMoves[i]}</td></tr>`;
            }

            this.moveTable = '<table >' + tableHeader + initMovesTr + levelUpMovesTr + '</table>';
        },
        showTypes : function() {
            if (this.typeBtnMsg === 'タイプを非表示') {
                this.typeBtnMsg = 'タイプを表示';
                this.typeTable = '';
                return;
            }

            this.typeBtnMsg = 'タイプを非表示';

            let typeTr = '';
            for (let i in this.Pikachu.type) {
                typeTr += `<tr><td>タイプ${i}</td><td>${this.Pikachu.type[i]}</td></tr>`;
            }

            this.typeTable = '<table >' + typeTr + '</table>';
        }
    }
}

export default PokemonObj
</script>