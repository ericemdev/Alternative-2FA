<script>
// @ts-nocheck
  import { Link } from "svelte-routing";
    let sidebarVisible = false;
  
    function toggleSidebar(){
      sidebarVisible = !sidebarVisible;
    }
  </script>
<main>
      <button on:click={toggleSidebar}>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="#db4938" class="w-12 h-12">
            <path d="M18.75 12.75h1.5a.75.75 0 0 0 0-1.5h-1.5a.75.75 0 0 0 0 1.5ZM12 6a.75.75 0 0 1 .75-.75h7.5a.75.75 0 0 1 0 1.5h-7.5A.75.75 0 0 1 12 6ZM12 18a.75.75 0 0 1 .75-.75h7.5a.75.75 0 0 1 0 1.5h-7.5A.75.75 0 0 1 12 18ZM3.75 6.75h1.5a.75.75 0 1 0 0-1.5h-1.5a.75.75 0 0 0 0 1.5ZM5.25 18.75h-1.5a.75.75 0 0 1 0-1.5h1.5a.75.75 0 0 1 0 1.5ZM3 12a.75.75 0 0 1 .75-.75h7.5a.75.75 0 0 1 0 1.5h-7.5A.75.75 0 0 1 3 12ZM9 3.75a2.25 2.25 0 1 0 0 4.5 2.25 2.25 0 0 0 0-4.5ZM12.75 12a2.25 2.25 0 1 1 4.5 0 2.25 2.25 0 0 1-4.5 0ZM9 15.75a2.25 2.25 0 1 0 0 4.5 2.25 2.25 0 0 0 0-4.5Z" />
          </svg>
          </button>
  
      {#if sidebarVisible}
          <nav style="left: {sidebarVisible ? '0%' : '-100%'};">
            <h1>Authenticator</h1>
              <button class="close-button" on:click={toggleSidebar} p-30>×</button>
              <ul>
                <button on:click={toggleSidebar} class=" btn-1"><Link to="/">Back Home</Link></button> <br>
                <button on:click={toggleSidebar} class="btn-2"><Link to="/Functionality">How It Works</Link></button>
                <button on:click={toggleSidebar} class="btn-3" ><Link to="/Settings">Help & Feedback</Link></button>
            
              </ul>
            </nav>
      {/if}
</main> 
  <style>
    nav {
      position: fixed;
      top: 0;
      width: 200px; 
      height: 100vh;
      background-color: beige;
      color: royalblue;
      transition: left 0.5s ease;
      left: -100%; 
      padding-left: 20px;
      padding-top: 10%;
    }
    h1{
      font-size: large;
      font-weight: bolder;
      text-align: center;
      position: fixed;
      top: 0;
      left: 45px;
    }
    
    .close-button {
      cursor: pointer;
      color: #db4938;
      font-size: 21px;
    }
    .btn-1{
      border-bottom: 2rem;
      padding: 20%;
    }
    .btn-2, .btn-3 {
          border-top: 3px solid grey;
          border-bottom: 1px solid grey;
          padding: 2rem;
    }
    .btn-3{
      position: fixed;
      bottom: 4%;
      left: 2%;
    }
    @media (min-width: 768px) {
    main{
      display: none;
    }
  }
  </style>