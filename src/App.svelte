<script>
 import Three from './component/3d.svelte'
 import Clockc from './component/clockc.svelte'

 $: marker = true;

 $: textButt = "Показать часы"
 let box;
 const handleClick = ()=> {
     marker = !marker ;
     if (marker) {
       import('./component/3d.svelte').then(res => box = res.default)
       textButt = "Показать часы "
     }
     else {
       import('./component/clockc.svelte').then(res => box = res.default)
       textButt = "Показать 3D модель"
     }

 };
 handleClick();
</script>

<main>
  <div>
    <header>
      <div class="logo">
        <div class="img">MK</div>
        <div class="text">Melekhin Konstantin</div>
      </div>
      <div class="menu">
        <div class="divMenu">Один</div>
        <div class="divMenu">Два</div>
        <div class="divMenu">Три</div>
      </div>
    </header>
  </div>

  <div class="center">
    <div class="world">
      <div class="scene-container">
        <svelte:component this="{box}" />

      </div> </div>
    <div class="about"> <h1>Всем привет</h1> <p>Эта страничка была созданна с помошью SVELTE и Thee.js
      <br> для ознакомления с функционалом.
      <br>
      <br> Кнопка реализует функцию: dynamic import component
      <br> которая заменяет один компонент на другой
    </p>
    <div class="buttons"> <button class="change" on:click={handleClick}  >{textButt}</button> </div>
    </div>

  </div>
  <div>
    <div class="footer">
      <div class="footerlinks-ul">
        <div class="footerlinks-li">Facebook</div>
        <div class="footerlinks-li">Instagram</div>
        <div class="footerlinks-li">Youtube</div>
      </div>
      <div class="copyright"> © 2022  </div>
    </div>
  </div>
</main>

<style>

  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 10em;
  }
  .footer {
    color: hsla(0,0%,100%,.4);
    display: flex;
    justify-content: space-between;
    border-top: 2px solid #333;
    padding-top: 1em ;
    margin-top: 6em;
  }
  .footerlinks-ul{
    display: flex;
    gap: 2em;
  }
  .logo {
    display: flex;
  }

  .img {
    width: fit-content;
    font-family: sans-serif;
    font-weight: bold;

    border-radius: 50%;
    color: white;
    padding: 0.5em;
    background-color: #007ced;
  }

  .text {
    color: white;
    padding: 0.5em;

  }
  .menu {
    display: flex;
    gap: 2em;
    color: hsla(0,0%,100%,.4);

  }
  .center{
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    gap: 5em;
  }
  .world{

    width: 370px;
    height: 370px;
    border-radius: 50%;
    overflow:hidden;
    border: 10px solid  #444;

    background-color: cornflowerblue;
    display: flex;
    align-items: center;
    justify-content: center;

  }
  .about {
    color: white;
     display: flex;
    flex-direction: column;
    gap: 2em;
  }
  .scene-container {
    position: relative;

    width: 370px;
    height: 370px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;

  }
  .divMenu:hover{
    cursor: pointer;
    opacity: 0.3;
  }
  button {

    border: 3px solid #007ced;
    background: #222;
    color: white;
    border-radius: 30px;
    padding: 1em;
  }

</style>
