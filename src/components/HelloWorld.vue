<template>
  <div>
    <br />
    <button @click="randomStart()" class="btn btn-danger">START{{Label}}</button>
    <div class="row">
      <div class="col-12">
        <button @click="randomDamage()" class="btn btn-warning">Attack{{Label}}</button>
        <button @click="randomSpDamage()" class="btn btn-primary">Special Attack{{Label}}</button>
      </div>
    </div>

    <p v-if="hp1 <= -1 ">
      <img
        src="https://media1.tenor.com/images/55e44350a50c7d380d625e72b11b9566/tenor.gif?itemid=4669333"  
      />
    </p>
    <p v-else-if="hp2 <= -1 ">
      <img
        src="https://media1.tenor.com/images/44cc605f115b3e09f6f26e22f6c87052/tenor.gif?itemid=11471626"
      />
    </p>

    <div class="row">
      <div class="col-4">
        <p>{{randomPlayer}}</p>
        <p>Health Point : {{hp1}}</p>
        <img :src="image1" />
      </div>

      <div class="col-4">
        <br />
        <br />
        <br />
        
        <img
          src="/img/2.png" width="350"        />
      </div>

      <div class="col-4">
        <p>{{randomMonster}}</p>
        <p>Health Point : {{hp2}}</p>
        <img :src="image2" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      randomPlayerAttack: "",
      randomMonsterAttack: "",
      randomSpAttack: "",
      image1: "",
      image2: "",
      hp1: " ",
      hp2: " ",

      player: [
        {
          name: "Yasuo",
          hp: 250,
          image:
            "/img/yasuo.png",
        },
        {
          name: "Nobita",
          hp: 200,
          image:
            "/img/nobita.png",
        },
        {
          name: "Manny Pacquiao",
          hp: 250,
          image:
            "/img/pacman.png",
        },
        {
          name: "Jerry",
          hp: 205,
          image:
            "/img/jerry.png",   
        },
        {
          name: "B1B2",
          hp: 190,
          image:
            "/img/b1b2.png",
        },
        {
          name: "Godzilla",
          hp: 210,
          image:
            "/img/godzilla.png",
        },

      ],
      randomPlayer: "",
      //ค่าพลังของ ตัวละคร เข้าถึงโดย player[1].hp -= 20
      monster: [
        {
          name: "Zad",
          hp: 250,
          image:
            "/img/zad.png"
        },
        {
          name: "Nohara Shinnosuke",
          hp: 220,
          image:
            "/img/cinjang.png",
        },
        {
          name: "Jack Sparrow",
          hp: 210,
          image:
            "/img/jack.png",
        },
        {
          name: "Tom",
          hp: 200,
          image:
            "/img/tom.png",
        },
        {
          name: "Tinky Winky",
          hp: 190,
          image:
            "/img/tinky wikky.png",
        },
        {
          name: "Obtimus prime",
          hp: 230,
          image:
            "/img/optimus.png",
        },




      ],
      randomMonster: "",
    };
  },
  props: {
    Label: String,
  },
  methods: {
    randomStart: function () {
      var chosenNumber1 = Math.floor(Math.random() * this.player.length);
      this.randomPlayer = this.player[chosenNumber1].name;
      this.hp1 = this.player[chosenNumber1].hp;
      this.image1 = this.player[chosenNumber1].image;
      var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
      this.randomMonster = this.monster[chosenNumber2].name;
      this.hp2 = this.monster[chosenNumber2].hp;
      this.image2 = this.monster[chosenNumber2].image;
    },
    randomDamage: function () {
      this.randomPlayerAttack = Math.max(Math.floor(Math.random() * 10) + 1, 3);
      this.hp2 -= this.randomPlayerAttack;
      this.randomMonsterAttack = Math.max(
        Math.floor(Math.random() * 15) + 1,
        5
      );
      this.hp1 -= this.randomMonsterAttack;
    },
    randomSpDamage: function () {
      this.randomPlayerAttack = Math.max(
        Math.floor(Math.random() * 20) + 1,
        10
      );
      this.hp2 -= this.randomPlayerAttack;
      this.randomMonsterAttack = Math.max(
        Math.floor(Math.random() * 15) + 1,
        5
      );
      this.hp1 -= this.randomMonsterAttack;
    },
  },
};
</script>

<style>
</style>