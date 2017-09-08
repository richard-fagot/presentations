/**
 * @author Malek Hamadi
 * @file Gestion des boutons communautaires
 * Pour le domaine .lefigaro.fr
 * @version uncompressed
 * base62 encoded & shrinked variables
 */

// Détermine l'url premium hôte des différents services.
var premiumHost;
if (typeof premiumServicesHost != 'undefined' && premiumServicesHost.match('((http|https):((//)|(\\\\))+[\w\d:#@%/;$()~_?\+-=\\\.&]*)')) {
  premiumHost = premiumServicesHost;
}
else {
  // Sinon sion est sur une url premium on prend l'url comme hote du service
  // Ou alors a défaut on pointe vers plus.lefigaro.fr
  premiumHost = (document.location.host.match('premium')) ? document.location.host : 'plus.lefigaro.fr';
  premiumHost = document.location.protocol +'//'+ premiumHost;
}

//Si fpAuth n'est pas chargé dans la page on s'occupe de le faire.
if (typeof fpauthentificator == 'undefined') {
  // Ajout du script fpAuth.
  var fpAuthRepo = '/sites/default/modules/fp/fp_user_services/scripts/fp_auth.js';
  if (document.body) {
    var script = document.createElement('script');
    script.setAttribute('src', premiumHost + fpAuthRepo);
    script.setAttribute('type', 'text/javascript');
    document.getElementsByTagName('head')[0].appendChild(script);
  }
  else {
    document.write('<script type="text/javascript" charset="UTF-8" src="'+ premiumHost + fpAuthRepo +'?20121213" ></script>');
  }
}
