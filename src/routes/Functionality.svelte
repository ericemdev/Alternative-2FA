<!-- Functionality.svelte -->

<script>
  
      let generateContent = {
        title: "Code Generation",
        description: "Generate secure and time-sensitive 2FA codes effortlessly. Navigate to the 'Home page' section, and press on the 'add Icon'. You can either add set up key manually or scan QR code, obtain a fresh authentication code that adds an extra layer of security to your accounts."
      };
    
      let saveContent = {
        title: "Code Backup",
        description: "Take control of your security by saving generated codes for future use. Click the 'Download-arrow' button, and you'll have the option to store your codes in a file. Choose a secure location, like a flash drive, to keep your codes accessible even in unexpected situations."
      };
    
      let restoreContent = {
        title: "Code Restoration",
        description: "Retrieve your saved codes whenever needed. Access the 'Upload -arrow' section, click the corresponding button, and select the file containing your saved codes. It's a quick and convenient way to regain access to your accounts without the hassle of manual code generation."
      };
    
      let additionalInfo = `
        Protect Your Saved Codes:
        Keep the files containing your 2FA codes in secure locations, such as encrypted drives or personal storage devices. Avoid sharing them on public platforms.
       
      `;
    </script>
   
    
    <h1>How It Works</h1>
    
    <section>
      <div class="generate">
        <h2>{generateContent.title}</h2>
        <p>{generateContent.description}</p>
      </div>
    
      <div class="save">
        <h2>{saveContent.title}</h2>
        <p>{saveContent.description}</p>
      </div>
    
      <div class="restore">
        <h2>{restoreContent.title}</h2>
        <p>{restoreContent.description}</p>
      </div>
    
      <p>{additionalInfo}</p>
    </section>
  
    <style>

        *{
            padding-top: 15%;
        }
        h1{
          border-bottom: 0.5rem solid rgb(201, 209, 181);
          border-left: 2%;
        }

       h1, h2, p {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        font-weight: 900;
        color: #A83737;
      }
    
      section {
        max-width: 800px;
        margin: 0 auto;
        padding: 20px;
        line-height: 1.6;
      }
    
      h1 {
        color: #333;
        text-align: center;
        margin-bottom: 2rem;
      }
    
      h2 {
        color: #007BFF;
        margin-bottom: 1rem;
        font-weight: bolder;
        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
      }
    
      .generate, .save, .restore {
        background-color: #f9f9f9;
        padding: 20px;
        margin-bottom: 20px;
        border-radius: 8px;
        box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      }
    
      p {
        color: #555; 
      }
    
  
      section > p {
        background-color: #000000; 
        color: #ffffff; 
        border: 1px solid #ffeeba;
        border-radius: 8px;
        padding: 20px;
        margin-top: 20px;
      }
    </style>