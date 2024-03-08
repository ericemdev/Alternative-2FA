<script>
// @ts-nocheck
import {Link} from "svelte-routing";

import Codes from "./pages/Codes.svelte";
import Sidebar from "./pages/sidebar.svelte";
import Settings from "./routes/Help&feedback.svelte";
import Functionality from "./routes/Functionality.svelte";
  import { Router, Route } from "svelte-routing";

  if ("serviceWorker" in navigator)
    navigator.serviceWorker.register("/serviceWorker.js")
      .then(() => console.log("Service Worker Registered"))
      .catch(err => console.error("Failed to register Cache service worker", err))

  import "./style.css"
</script>
<svelte:head> 
  <title>2FA</title>
</svelte:head>
   <nav>
    <h1>2-FA</h1>
   </nav>
    <Router>
      <Sidebar />
      <Route path="/" component={Codes}/>
      <Route path="/Settings" component={Settings} />
      <Route path="/Functionality" component={Functionality}/>
    </Router>


<style>


  h1 {
    margin-right: 10px;
    font-size: larger;
    font-weight: bold;
    color: #db4938;
    float: right;
  }

  @media (min-width: 768px) {
    *{
      display: none;
    }
  }
</style>
