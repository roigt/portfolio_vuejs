<script setup>
 import SocialIcon from "@/components/SocialIcon.vue";
</script>

<template>
  <div id="top-line">
    <img id="profile-img" src="../assets/maPhoto2.png" alt="julio roigt" width="200px" height="200px"/>

    <div id="line">
      <p>Je suis <span class="text-highlight-1">Julio Roigt</span>, <br/>
        Ingénieur logiciel en informatique
      </p>

      <div id="social">
          <SocialIcon link="https://www.linkedin.com/in/julio-roigt-07b6071b4/" icon="linkedin" alt="linkedin "  id="icon" />
          <SocialIcon link="https://github.com/roigt" icon="github" alt=" github" id="icon"/>
      </div>
      <div class="contact-infos">
        <small>📞 Tel : +33 07 63 92 43 50</small>
        <small>✉️ Email : griezmanjulio@yahoo.com</small>
      </div>
    </div>
  </div>

</template>

<style scoped>
   #top-line {
     margin-top: 50px;
     width: 100%;
     height: 300px;

   }

   #top-line #profile-img {
     float: left;
     margin-right: 50px;
     border-radius: 50%;
     text-shadow: #f2f2f2 0px 8px 8px;
   }

   #top-line #line{
     float: left;
     transform:translateY(10%);
     text-align: center;

   }

   #top-line p{
     font-size: 48px;
     line-height: 60px;
   }
   #top-line p span{
     font-weight: bold;
   }



   @media screen and (max-width: 905px) {
     #top-line #profile-img {
       display: none;
     }

     #top-line #line{
       float:none;
       transform: translateY(0%);
     }

     #top-line p{
       font-size: 28px;
     }

   }
   .contact-infos {
     display: flex;
     justify-content: center;
     align-items: center;
     flex-wrap: wrap; /* permet le retour à la ligne */
     gap: 25px; /* espace horizontal/vertical */
     margin-top: 25px;
     font-size: 0.95rem;
     color: #dcdcdc;
     text-align: center;
   }

   /* Style des éléments individuels */
   .contact-infos small {
     background: rgba(255, 255, 255, 0.05);
     padding: 10px 18px;
     border-radius: 8px;
     border: 1px solid rgba(255, 255, 255, 0.1);
     transition: all 0.3s ease;
     word-break: break-word;
   }

   /* Effet au survol */
   .contact-infos small:hover {
     color: #00d1ff;
     border-color: #00d1ff;
     box-shadow: 0 0 10px #00d1ff;
   }

   /* 📱 Mobile : on réduit l’espacement et la taille */
   @media (max-width: 600px) {
     .contact-infos {
       flex-direction: column;
       gap: 12px;
       font-size: 0.9rem;
     }

     .contact-infos small {
       width: 100%;
       max-width: 320px;
       text-align: center;
     }
   }


</style>