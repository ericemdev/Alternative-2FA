<script>
    import OTP from '../totp.js'

    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    export let otp;
    setInterval(() => {
        const token = new OTP(otp.secret);
        otp.code = token.getToken();
          otp.time = Math.floor(token.getRemainingSeconds());
    }, 1000);

    let copying = false, copy = () => {
        navigator.clipboard.writeText(otp.code);
        copying = true; setTimeout(() => copying=false, 2000);
    }
</script>


<li class="flex justify-between p-8 border-t border-b">
    <div>
        <h2><span>{otp.issuer}</span></h2>
        <p>
            <span class:seconds-low={otp.time <= 0}>{otp.code}</span>
        </p>
        
    </div>
    
    <button on:click={copy} class:opacity-20={copying}>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="w-4 h-4">
            <path d="M5.5 3.5A1.5 1.5 0 0 1 7 2h2.879a1.5 1.5 0 0 1 1.06.44l2.122 2.12a1.5 1.5 0 0 1 .439 1.061V9.5A1.5 1.5 0 0 1 12 11V8.621a3 3 0 0 0-.879-2.121L9 4.379A3 3 0 0 0 6.879 3.5H5.5Z" />
            <path d="M4 5a1.5 1.5 0 0 0-1.5 1.5v6A1.5 1.5 0 0 0 4 14h5a1.5 1.5 0 0 0 1.5-1.5V8.621a1.5 1.5 0 0 0-.44-1.06L7.94 5.439A1.5 1.5 0 0 0 6.878 5H4Z" />
        </svg>
    </button>

    <button on:click={() => dispatch("remove")}>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="#db4938" class="w-4 h-4">
            <path d="M5.28 4.22a.75.75 0 0 0-1.06 1.06L6.94 8l-2.72 2.72a.75.75 0 1 0 1.06 1.06L8 9.06l2.72 2.72a.75.75 0 1 0 1.06-1.06L9.06 8l2.72-2.72a.75.75 0 0 0-1.06-1.06L8 6.94 5.28 4.22Z" />
        </svg>
    </button>
   
    <div>{otp.time}</div>
</li>

<style>
  

    p{
        color: rgb(0, 0, 248);
        text-transform: uppercase;
        font-size: 18px;
        font-weight: bolder;
        font-family: 'Roboto', sans-serif;
    }
  h2{
    color: #000000;
    font-weight: bolder;
  }
  .seconds-low {
        color: red;
    }
</style>