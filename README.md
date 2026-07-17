# mailsur-site 
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MailSûr — Votre messagerie professionnelle sécurisée</title>
<style>
  :root{
    --ink:#12181b; --paper:#faf6ee; --paper-2:#f1ebdb;
    --brass:#b8863b; --brass-dark:#8f6428;
    --forest:#1f4b3f; --forest-2:#173a31;
    --line:#dcd3bd; --muted:#6b6355;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  body{font-family:Georgia,'Times New Roman',serif;background:var(--paper);color:var(--ink);line-height:1.55;}
  h1,h2,h3,.brand{font-family:'Palatino Linotype',Palatino,Georgia,serif;font-weight:700;}
  .wrap{max-width:1120px;margin:0 auto;padding:0 28px;}
  header{position:sticky;top:0;z-index:50;background:var(--paper);border-bottom:1px solid var(--line);}
  nav.wrap{display:flex;align-items:center;justify-content:space-between;height:76px;}
  .brand{display:flex;align-items:center;gap:10px;font-size:22px;color:var(--forest-2);}
  .brand .mark{width:34px;height:34px;border-radius:8px;background:var(--forest-2);display:flex;align-items:center;justify-content:center;color:var(--paper);font-size:17px;}
  nav ul{list-style:none;display:flex;gap:34px;font-size:15px;}
  nav ul a{text-decoration:none;color:var(--ink);opacity:.8;}
  .nav-cta{background:var(--forest-2);color:var(--paper);padding:10px 20px;text-decoration:none;font-size:14px;}
  .hero{padding:96px 0 0;border-bottom:1px solid var(--line);}
  .kicker{display:inline-block;font-size:13px;letter-spacing:2.5px;text-transform:uppercase;color:var(--brass-dark);border-bottom:1px solid var(--brass);padding-bottom:6px;margin-bottom:26px;}
  .hero h1{font-size:clamp(36px,5vw,58px);color:var(--forest-2);max-width:780px;line-height:1.12;margin-bottom:22px;}
  .hero p.lead{font-size:19px;color:var(--muted);max-width:560px;margin-bottom:34px;}
  .hero-actions{display:flex;gap:16px;flex-wrap:wrap;align-items:center;margin-bottom:54px;}
  .btn-primary{background:var(--brass);color:#fff;padding:15px 30px;text-decoration:none;font-size:15px;}
  .btn-ghost{padding:15px 26px;text-decoration:none;color:var(--forest-2);border-bottom:1px solid var(--forest-2);}
  .stats-bar{border-top:1px solid var(--line);display:grid;grid-template-columns:repeat(4,1fr);}
  .stat{padding:30px 28px;border-left:1px solid var(--line);}
  .stat:first-child{border-left:none;padding-left:0;}
  .stat .stat-num{font-size:30px;color:var(--forest-2);font-family:Georgia,serif;margin-bottom:4px;}
  .stat .stat-label{font-size:13px;color:var(--muted);}
  section{padding:88px 0;border-bottom:1px solid var(--line);}
  .section-head{max-width:640px;margin-bottom:56px;}
  .section-head p{color:var(--muted);margin-top:14px;font-size:17px;}
  .section-head h2{font-size:clamp(28px,3.4vw,40px);color:var(--forest-2);}
  .features-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--line);border:1px solid var(--line);}
  .feature{background:var(--paper);padding:38px 32px;}
  .feature .num{color:var(--brass);font-size:14px;margin-bottom:18px;display:block;}
  .feature h3{font-size:20px;margin-bottom:12px;color:var(--forest-2);}
  .feature p{color:var(--muted);font-size:15px;}

  .security-wrap{display:grid;grid-template-columns:1fr 1fr;gap:64px;align-items:center;}
  .security-list{list-style:none;}
  .security-list li{display:flex;gap:18px;padding:20px 0;border-top:1px solid var(--line);}
  .security-list li:first-child{border-top:none;}
  .sec-icon{width:38px;height:38px;flex-shrink:0;border:1px solid var(--brass);border-radius:50%;display:flex;align-items:center;justify-content:center;color:var(--brass-dark);font-size:16px;}
  .security-list h4{color:var(--forest-2);font-size:16.5px;margin-bottom:4px;}
  .security-list p{color:var(--muted);font-size:14.5px;}
  .security-visual{background:var(--forest-2);color:var(--paper);padding:48px;position:relative;min-height:340px;display:flex;flex-direction:column;justify-content:center;}
  .security-visual .quote-mark{font-size:60px;color:var(--brass);line-height:1;margin-bottom:10px;}
  .security-visual p{font-size:19px;line-height:1.5;margin-bottom:20px;}
  .security-visual .sig{font-size:14px;color:#cfe0d8;}

  .pricing-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;}
  .plan{background:var(--paper);border:1px solid var(--line);padding:40px 32px;display:flex;flex-direction:column;position:relative;}
  .plan.featured{background:var(--forest-2);color:var(--paper);border-color:var(--forest-2);}
  .plan.featured .plan-desc{color:#cfe0d8;}
  .badge{position:absolute;top:-13px;right:32px;background:var(--brass);color:#fff;font-size:11px;letter-spacing:1.5px;text-transform:uppercase;padding:6px 12px;}
  .plan-name{font-size:15px;letter-spacing:1.5px;text-transform:uppercase;margin-bottom:18px;color:var(--brass-dark);}
  .plan.featured .plan-name{color:var(--brass);}
  .plan-price{font-size:42px;margin-bottom:6px;}
  .plan-price small{font-size:15px;color:var(--muted);font-weight:normal;}
  .plan-desc{color:var(--muted);font-size:14px;margin-bottom:28px;}
  .plan ul{list-style:none;margin-bottom:32px;flex:1;}
  .plan ul li{padding:10px 0;border-top:1px solid var(--line);font-size:14.5px;display:flex;gap:10px;}
  .plan.featured ul li{border-top:1px solid #2c5c4d;}
  .plan ul li::before{content:"—";color:var(--brass);flex-shrink:0;}
  .plan-btn{display:block;text-align:center;padding:14px;text-decoration:none;font-size:14.5px;border:1px solid var(--forest-2);color:var(--forest-2);}
  .plan.featured .plan-btn{background:var(--brass);border-color:var(--brass);color:#fff;}

  .testimonial-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:28px;}
  .testimonial{border:1px solid var(--line);padding:32px 28px;background:var(--paper-2);}
  .stars{color:var(--brass);font-size:15px;margin-bottom:16px;letter-spacing:2px;}
  .testimonial p{font-size:15px;color:var(--ink);margin-bottom:22px;font-style:italic;}
  .t-author{display:flex;align-items:center;gap:12px;}
  .t-avatar{width:38px;height:38px;border-radius:50%;background:var(--forest-2);color:var(--paper);display:flex;align-items:center;justify-content:center;font-size:14px;}
  .t-name{font-size:14px;color:var(--forest-2);}
  .t-role{font-size:12.5px;color:var(--muted);}

  .steps{display:grid;grid-template-columns:repeat(4,1fr);gap:30px;}
  .step{padding-top:24px;border-top:2px solid var(--brass);}
  .step .step-num{font-size:13px;letter-spacing:2px;color:var(--brass-dark);margin-bottom:14px;}
  .step h3{font-size:17px;margin-bottom:10px;color:var(--forest-2);}
  .step p{color:var(--muted);font-size:14.5px;}

  .signup-box{background:var(--forest-2);color:var(--paper);padding:64px;display:grid;grid-template-columns:1fr 1fr;gap:56px;align-items:center;}
  .signup-box h2{font-size:30px;margin-bottom:16px;}
  .signup-box p{color:#cfe0d8;}
  form.signup{display:flex;flex-direction:column;gap:14px;}
  form.signup input, form.signup select{padding:14px 16px;border:1px solid #2c5c4d;background:#173a31;color:#fff;font-size:15px;}
  form.signup input::placeholder{color:#9fbdb0;}
  form.signup label{font-size:13px;color:#cfe0d8;margin-bottom:-6px;}
  form.signup button{margin-top:8px;background:var(--brass);color:#fff;border:none;padding:15px;font-size:15px;cursor:pointer;}
  .form-note{font-size:12.5px;color:#9fbdb0;margin-top:4px;}
  .form-success{display:none;background:#2c5c4d;border:1px solid var(--brass);padding:16px 18px;font-size:14px;margin-top:10px;}

  .faq-item{border-top:1px solid var(--line);padding:26px 0;}
  .faq-item:last-child{border-bottom:1px solid var(--line);}
  .faq-q{display:flex;justify-content:space-between;align-items:center;cursor:pointer;font-size:18px;color:var(--forest-2);}
  .faq-q .plus{font-size:22px;color:var(--brass);transition:transform .2s;}
  .faq-item.open .plus{transform:rotate(45deg);}
  .faq-a{max-height:0;overflow:hidden;transition:max-height .3s ease;color:var(--muted);font-size:15px;}
  .faq-item.open .faq-a{max-height:200px;margin-top:14px;}

  footer{padding:56px 0 40px;}
  .footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:40px;margin-bottom:48px;}
  footer h4{font-size:14px;color:var(--forest-2);margin-bottom:16px;}
  footer ul{list-style:none;}
  footer ul li{margin-bottom:10px;}
  footer ul a{text-decoration:none;color:var(--muted);font-size:14.5px;}
  footer p.about{color:var(--muted);font-size:14.5px;max-width:320px;}
  .footer-bottom{border-top:1px solid var(--line);padding-top:24px;display:flex;justify-content:space-between;color:var(--muted);font-size:13px;flex-wrap:wrap;gap:10px;}

  @media (max-width:860px){
    nav ul{display:none;}
    .features-grid{grid-template-columns:1fr;}
    .pricing-grid{grid-template-columns:1fr;}
    .steps{grid-template-columns:1fr 1fr;}
    .signup-box{grid-template-columns:1fr;padding:40px 28px;}
    .footer-grid{grid-template-columns:1fr 1fr;}
    .stats-bar{grid-template-columns:1fr 1fr;}
    .stat{border-left:none;border-top:1px solid var(--line);padding-left:0;}
    .security-wrap{grid-template-columns:1fr;}
    .testimonial-grid{grid-template-columns:1fr;}
  }
</style>
</head>
<body>
<header>
  <nav class="wrap">
    <div class="brand"><span class="mark">M</span>MailSûr</div>
    <ul>
      <li><a href="#fonctionnalites">Fonctionnalités</a></li>
      <li><a href="#securite">Sécurité</a></li>
      <li><a href="#tarifs">Tarifs</a></li>
      <li><a href="#avis">Avis</a></li>
      <li><a href="#faq">FAQ</a></li>
    </ul>
    <a href="#inscription" class="nav-cta">Créer un compte</a>
  </nav>
</header>

<section class="hero">
  <div class="wrap">
    <span class="kicker">Messagerie professionnelle · Abidjan, Côte d'Ivoire</span>
    <h1>Une boîte mail sérieuse pour votre entreprise, hébergée et protégée.</h1>
    <p class="lead">MailSûr vous offre une adresse email professionnelle (@votreentreprise.ci), un chiffrement de bout en bout et un stockage fiable — sans publicité, sans revente de vos données.</p>
    <div class="hero-actions">
      <a href="#tarifs" class="btn-primary">Voir les tarifs</a>
      <a href="#comment" class="btn-ghost">Comment ça marche →</a>
    </div>
  </div>
  <div class="stats-bar wrap">
    <div class="stat"><div class="stat-num">99,9 %</div><div class="stat-label">Disponibilité garantie</div></div>
    <div class="stat"><div class="stat-num">24h/24</div><div class="stat-label">Surveillance des serveurs</div></div>
    <div class="stat"><div class="stat-num">&lt; 24h</div><div class="stat-label">Activation du compte</div></div>
    <div class="stat"><div class="stat-num">0</div><div class="stat-label">Publicité dans vos emails</div></div>
  </div>
</section>

<section id="fonctionnalites">
  <div class="wrap">
    <div class="section-head">
      <span class="kicker">Fonctionnalités</span>
      <h2>Tout ce qu'il faut pour une messagerie d'entreprise sérieuse</h2>
      <p>Conçu pour les PME, cabinets et indépendants ivoiriens qui veulent une image professionnelle et des données protégées.</p>
    </div>
    <div class="features-grid">
      <div class="feature"><span class="num">01</span><h3>Adresse à votre domaine</h3><p>contact@votreentreprise.ci — une adresse professionnelle qui inspire confiance à vos clients.</p></div>
      <div class="feature"><span class="num">02</span><h3>Chiffrement de bout en bout</h3><p>Vos échanges sensibles restent confidentiels, protégés du serveur jusqu'au destinataire.</p></div>
      <div class="feature"><span class="num">03</span><h3>Filtrage anti-spam avancé</h3><p>Moins de courrier indésirable, plus de temps pour l'essentiel.</p></div>
      <div class="feature"><span class="num">04</span><h3>Stockage extensible</h3><p>De 5 Go à 100 Go selon votre forfait, avec extension possible à tout moment.</p></div>
      <div class="feature"><span class="num">05</span><h3>Accès multi-appareils</h3><p>Web, mobile et applications de messagerie classiques (IMAP/SMTP inclus).</p></div>
      <div class="feature"><span class="num">06</span><h3>Sauvegardes automatiques</h3><p>Vos emails et contacts sauvegardés chaque jour, restaurables en un clic.</p></div>
    </div>
  </div>
</section>

<section id="securite">
  <div class="wrap">
    <div class="section-head">
      <span class="kicker">Confiance & sécurité</span>
      <h2>Vos échanges professionnels méritent d'être protégés</h2>
    </div>
    <div class="security-wrap">
      <ul class="security-list">
        <li><div class="sec-icon">🔒</div><div><h4>Chiffrement de bout en bout</h4><p>Vos messages sensibles restent illisibles pour quiconque n'est pas le destinataire prévu.</p></div></li>
        <li><div class="sec-icon">🛡</div><div><h4>Aucune revente de données</h4><p>Contrairement aux services gratuits, votre contenu n'est jamais analysé à des fins publicitaires.</p></div></li>
        <li><div class="sec-icon">⟳</div><div><h4>Sauvegardes quotidiennes</h4><p>Vos emails sont sauvegardés chaque jour et restaurables en cas d'incident.</p></div></li>
        <li><div class="sec-icon">✓</div><div><h4>Authentification renforcée</h4><p>Double authentification disponible pour empêcher tout accès non autorisé.</p></div></li>
      </ul>
      <div class="security-visual">
        <div class="quote-mark">"</div>
        <p>La confidentialité de vos échanges professionnels n'est pas une option — c'est la raison d'être de MailSûr.</p>
        <div class="sig">— L'équipe MailSûr</div>
      </div>
    </div>
  </div>
</section>

<section id="tarifs">
  <div class="wrap">
    <div class="section-head">
      <span class="kicker">Tarifs</span>
      <h2>Un forfait pour chaque taille d'entreprise</h2>
      <p>Facturation mensuelle ou annuelle (2 mois offerts sur l'engagement annuel). Sans engagement, résiliable à tout moment.</p>
    </div>
    <div class="pricing-grid">
      <div class="plan">
        <div class="plan-name">Basique</div>
        <div class="plan-price">3 000 F<small> / mois</small></div>
        <div class="plan-desc">Pour l'indépendant ou la petite structure qui démarre.</div>
        <ul><li>1 adresse email @votredomaine</li><li>5 Go de stockage</li><li>Anti-spam standard</li><li>Support par email</li></ul>
        <a href="#inscription" class="plan-btn">Choisir Basique</a>
      </div>
      <div class="plan featured">
        <span class="badge">Le plus choisi</span>
        <div class="plan-name">Pro</div>
        <div class="plan-price">7 500 F<small> / mois</small></div>
        <div class="plan-desc">Pour les PME et cabinets avec plusieurs collaborateurs.</div>
        <ul><li>Jusqu'à 5 adresses email</li><li>20 Go de stockage par adresse</li><li>Chiffrement de bout en bout</li><li>Anti-spam avancé</li><li>Support prioritaire (24h)</li></ul>
        <a href="#inscription" class="plan-btn">Choisir Pro</a>
      </div>
      <div class="plan">
        <div class="plan-name">Entreprise</div>
        <div class="plan-price">20 000 F<small> / mois</small></div>
        <div class="plan-desc">Pour les organisations avec des besoins étendus.</div>
        <ul><li>Adresses illimitées</li><li>100 Go de stockage par adresse</li><li>Administration centralisée</li><li>Sauvegardes quotidiennes</li><li>Support dédié par téléphone</li></ul>
        <a href="#inscription" class="plan-btn">Choisir Entreprise</a>
      </div>
    </div>
  </div>
</section>

<section id="avis">
  <div class="wrap">
    <div class="section-head">
      <span class="kicker">Témoignages</span>
      <h2>Ce que nos premiers utilisateurs en disent</h2>
    </div>
    <div class="testimonial-grid">
      <div class="testimonial">
        <div class="stars">★★★★★</div>
        <p>Depuis que nous avons une adresse à notre domaine, nos clients nous prennent beaucoup plus au sérieux dès le premier échange.</p>
        <div class="t-author"><div class="t-avatar">AK</div><div><div class="t-name">Aïcha Koffi</div><div class="t-role">Cabinet comptable, Abidjan</div></div></div>
      </div>
      <div class="testimonial">
        <div class="stars">★★★★★</div>
        <p>La mise en place a été rapide et le support répond vraiment vite. Exactement ce qu'il fallait pour notre petite équipe.</p>
        <div class="t-author"><div class="t-avatar">JB</div><div><div class="t-name">Jean-Baptiste Yao</div><div class="t-role">Agence immobilière</div></div></div>
      </div>
      <div class="testimonial">
        <div class="stars">★★★★★</div>
        <p>Enfin une solution locale qui comprend nos besoins, avec un paiement simple par Mobile Money.</p>
        <div class="t-author"><div class="t-avatar">FN</div><div><div class="t-name">Fatou N'Guessan</div><div class="t-role">Boutique en ligne</div></div></div>
      </div>
    </div>
  </div>
</section>

<section id="comment">
  <div class="wrap">
    <div class="section-head">
      <span class="kicker">Mise en route</span>
      <h2>Opérationnel en moins de 24 heures</h2>
    </div>
    <div class="steps">
      <div class="step"><div class="step-num">ÉTAPE 01</div><h3>Choisissez un forfait</h3><p>Sélectionnez l'offre adaptée à la taille de votre équipe.</p></div>
      <div class="step"><div class="step-num">ÉTAPE 02</div><h3>Renseignez votre domaine</h3><p>Utilisez un domaine existant ou faites-en réserver un pour vous.</p></div>
      <div class="step"><div class="step-num">ÉTAPE 03</div><h3>Réglez votre abonnement</h3><p>Par Mobile Money, carte bancaire ou virement.</p></div>
      <div class="step"><div class="step-num">ÉTAPE 04</div><h3>Recevez vos accès</h3><p>Vos adresses sont actives et prêtes à l'emploi sous 24h.</p></div>
    </div>
  </div>
</section>

<section id="inscription" style="border-bottom:none;padding-bottom:0;">
  <div class="wrap">
    <div class="signup-box">
      <div>
        <h2>Prêt à professionnaliser votre messagerie ?</h2>
        <p>Laissez-nous vos coordonnées, notre équipe vous recontacte sous 24h ouvrées pour activer votre compte.</p>
      </div>
      <form class="signup" id="signupForm">
        <div><label>Nom complet</label><input type="text" id="fullname" placeholder="Ex. Aïcha Koffi" required></div>
        <div><label>Nom de l'entreprise</label><input type="text" id="company" placeholder="Ex. Koffi & Associés" required></div>
        <div><label>Email de contact</label><input type="email" id="email" placeholder="vous@exemple.com" required></div>
        <div><label>Téléphone</label><input type="tel" id="phone" placeholder="+225 07 00 00 00 00" required></div>
        <div>
          <label>Forfait souhaité</label>
          <select id="plan">
            <option value="basique">Basique — 3 000 F/mois</option>
            <option value="pro" selected>Pro — 7 500 F/mois</option>
            <option value="entreprise">Entreprise — 20 000 F/mois</option>
          </select>
        </div>
        <button type="submit">Demander l'activation</button>
        <div class="form-note">Aucun prélèvement n'est effectué avant confirmation de votre commande.</div>
        <div class="form-success" id="formSuccess">Merci ! Votre demande a été enregistrée. Notre équipe vous contactera très prochainement.</div>
      </form>
    </div>
  </div>
</section>

<section id="faq">
  <div class="wrap">
    <div class="section-head">
      <span class="kicker">Questions fréquentes</span>
      <h2>Ce que vous voulez savoir</h2>
    </div>
    <div class="faq-list">
      <div class="faq-item"><div class="faq-q"><span>Puis-je garder mon domaine actuel ?</span><span class="plus">+</span></div><div class="faq-a">Oui, vous pouvez utiliser un domaine que vous possédez déjà. Nous vous accompagnons pour la configuration des enregistrements DNS.</div></div>
      <div class="faq-item"><div class="faq-q"><span>Comment se fait le paiement ?</span><span class="plus">+</span></div><div class="faq-a">Par Mobile Money (Orange, MTN, Moov), carte bancaire ou virement. La facturation est mensuelle ou annuelle.</div></div>
      <div class="faq-item"><div class="faq-q"><span>Puis-je changer de forfait plus tard ?</span><span class="plus">+</span></div><div class="faq-a">Oui, vous pouvez passer à un forfait supérieur ou inférieur à tout moment, sans frais de changement.</div></div>
      <div class="faq-item"><div class="faq-q"><span>Mes données sont-elles hébergées en Côte d'Ivoire ?</span><span class="plus">+</span></div><div class="faq-a">Nous travaillons avec des infrastructures fiables et pouvons discuter d'options d'hébergement local selon vos besoins de conformité.</div></div>
      <div class="faq-item"><div class="faq-q"><span>Puis-je résilier à tout moment ?</span><span class="plus">+</span></div><div class="faq-a">Oui, aucun engagement n'est requis pour les forfaits mensuels. Vos données restent exportables avant la clôture du compte.</div></div>
    </div>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="footer-grid">
      <div>
        <div class="brand" style="margin-bottom:16px;"><span class="mark">M</span>MailSûr</div>
        <p class="about">Messagerie professionnelle sécurisée pour les entreprises de Côte d'Ivoire. Basé à Abidjan.</p>
      </div>
      <div><h4>Produit</h4><ul><li><a href="#fonctionnalites">Fonctionnalités</a></li><li><a href="#tarifs">Tarifs</a></li><li><a href="#faq">FAQ</a></li></ul></div>
      <div><h4>Entreprise</h4><ul><li><a href="#">À propos</a></li><li><a href="#">Contact</a></li><li><a href="#">Mentions légales</a></li></ul></div>
      <div><h4>Légal</h4><ul><li><a href="#">Confidentialité</a></li><li><a href="#">Conditions d'utilisation</a></li></ul></div>
    </div>
    <div class="footer-bottom">
      <span>© 2026 MailSûr. Tous droits réservés.</span>
      <span>Abidjan, Côte d'Ivoire</span>
    </div>
  </div>
</footer>

<script>
  document.querySelectorAll('.faq-item').forEach(item => {
    item.querySelector('.faq-q').addEventListener('click', () => {
      const isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('open'));
      if(!isOpen) item.classList.add('open');
    });
  });
  document.getElementById('signupForm').addEventListener('submit', function(e){
    e.preventDefault();
    document.getElementById('formSuccess').style.display = 'block';
    this.reset();
    document.getElementById('plan').value = 'pro';
  });
</script>
</body>
</html>
