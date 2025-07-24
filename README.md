// Script JavaScript simulant le comportement de la boutique Netflix

// Offres disponibles
const offres = [
  { ecrans: 1, prix: 2500 },
  { ecrans: 2, prix: 3500 },
  { ecrans: 4, prix: 5000 }
];

// Méthodes de paiement
const paiements = ["Carte Visa", "Orange Money", "MTN Money", "Wave"];

// Afficher les offres dans la console
console.log("Nos Offres Netflix :");
offres.forEach((offre, index) => {
  console.log(`Offre ${index}: ${offre.ecrans} Écran(s) - ${offre.prix} FCFA`);
});

// Afficher les méthodes de paiement
console.log("\nMéthodes de Paiement acceptées :");
paiements.forEach((methode, index) => {
  console.log(`Méthode ${index}: ${methode}`);
});

// Fonction pour simuler l'envoi d'une commande
function envoyerCommande(nom, telephone, offreIndex, paiementIndex, message = "") {
  console.log("\nDébut de la fonction envoyerCommande...");
  console.log(`Paramètres reçus -> nom: ${nom}, téléphone: ${telephone}, offreIndex: ${offreIndex}, paiementIndex: ${paiementIndex}, message: ${message}`);

  if (!nom || !telephone || offreIndex === undefined || paiementIndex === undefined) {
    console.log("Tous les champs obligatoires doivent être remplis.");
    return;
  }

  const offreChoisie = offres[offreIndex];
  const paiementChoisi = paiements[paiementIndex];

  console.log("\nCommande envoyée avec succès !");
  console.log(`Nom: ${nom}`);
  console.log(`Téléphone: ${telephone}`);
  console.log(`Offre: ${offreChoisie.ecrans} Écran(s) - ${offreChoisie.prix} FCFA`);
  console.log(`Paiement: ${paiementChoisi}`);
  if (message) console.log(`Message: ${message}`);
  console.log("Fin de la fonction envoyerCommande.\n");
}

// Exemple d'utilisation
console.log("\n--- Exemple d'utilisation de la fonction envoyerCommande ---");
envoyerCommande("Jean Dupont", "+2250707070707", 1, 0, "Livrer dès que possible svp.");
