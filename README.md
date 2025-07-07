# Custom Scrollbar Premium pour Bubble

## Vue d'ensemble

Custom Scrollbar Premium est une évolution majeure du plugin original Custom Scrollbar, offrant des fonctionnalités avancées pour transformer les barres de défilement standard en éléments de design professionnels entièrement personnalisables. Idéal pour les développeurs et designers qui souhaitent une cohérence visuelle parfaite avec leur marque et une expérience utilisateur optimisée.

## Fonctionnalités Premium

### 1. Personnalisation visuelle avancée
- **Contrôle complet des dimensions** : largeur, hauteur, rayons de bordure
- **Personnalisation des couleurs** : couleur de base, survol, état actif
- **Effets visuels** : ombres, bordures, dégradés
- **Boutons de défilement** : personnalisation complète des flèches
- **Coins personnalisables** : style des intersections de barres de défilement

### 2. Adaptation responsive
- **Configuration mobile dédiée** : dimensions adaptées aux écrans tactiles
- **Media queries intégrées** : ajustements automatiques selon la taille d'écran

### 3. Mode sombre
- **Support natif du mode sombre** : détection automatique des préférences système
- **Thèmes personnalisables** : configurations spécifiques pour mode clair et sombre

### 4. Animations et effets
- **Effets de transition** : apparition/disparition fluide
- **Animations personnalisées** : pulsation, changements de couleur
- **Comportement de défilement** : lisse, par étapes ou instantané

### 5. API JavaScript
- **Contrôle dynamique** : modification des barres de défilement en temps réel
- **Sélecteurs ciblés** : application sur des éléments spécifiques
- **Actions programmables** : défilement automatique, masquage conditionnel

### 6. Intégration Bubble avancée
- **Actions de workflow** : contrôle des barres de défilement via l'interface Bubble
- **Conditions d'état** : détection de la position de défilement
- **Événements déclencheurs** : actions basées sur le comportement de défilement

## Installation et configuration

1. Installez le plugin depuis le Bubble Plugin Marketplace
2. Accédez à l'onglet Plugins dans votre éditeur Bubble
3. Configurez les paramètres de base et avancés selon vos besoins
4. Pour une personnalisation avancée, utilisez les sélecteurs CSS spécifiques

## Paramètres principaux

| Paramètre | Description | Valeur par défaut |
|-----------|-------------|-------------------|
| Width | Largeur de la barre verticale (px) | 10 |
| Height | Hauteur de la barre horizontale (px) | 10 |
| Track color | Couleur de fond de la piste | #f1f1f1 |
| Track shadow color | Couleur de l'ombre de la piste | rgba(0,0,0,0.1) |
| Shadow blur | Niveau de flou de l'ombre (px) | 5 |
| Scrollbar color | Couleur de la barre | #888 |
| Scrollbar color on hover | Couleur au survol | #555 |
| Scrollbar color on active | Couleur lors du clic/drag | #333 |
| Handle border radius | Arrondi des coins de la barre (px) | 10 |

## Utilisation de l'API JavaScript

```javascript
// Appliquer un style personnalisé à un élément
CustomScrollbar.applyTo('#mon-element', { 
  width: 12,
  trackColor: '#eaeaea',
  thumbColor: '#007bff', 
  scrollBehavior: 'smooth'
});

// Faire défiler vers une position spécifique
CustomScrollbar.scrollTo('#mon-element', { 
  top: 500, 
  left: 0,
  smooth: true 
});

// Masquer/afficher la barre de défilement
CustomScrollbar.toggle('#mon-element', true); // afficher
CustomScrollbar.toggle('#mon-element', false); // masquer

// Réinitialiser à la barre par défaut
CustomScrollbar.reset('#mon-element');
```

## Actions Bubble

### Apply Custom Scrollbar
- **Element ID** : ID ou classe de l'élément cible
- **Options** : Configuration JSON des propriétés de la barre

### Scroll To Position
- **Element ID** : ID ou classe de l'élément cible
- **Top Position** : Position verticale (px)
- **Left Position** : Position horizontale (px)
- **Smooth** : Animation de défilement (true/false)

### Toggle Scrollbar
- **Element ID** : ID ou classe de l'élément cible
- **Visible** : Afficher ou masquer (true/false)

## Événements Bubble

### On Scroll
Déclenché lorsque l'utilisateur fait défiler un élément spécifié.
- **Element ID** : ID de l'élément à surveiller
- **Scroll Position** : Position actuelle du défilement (px)
- **Scroll Percentage** : Pourcentage de défilement (0-100)

### On Scroll End
Déclenché lorsque l'utilisateur arrête de faire défiler.
- **Element ID** : ID de l'élément surveillé
- **Final Position** : Position finale du défilement

## Cas d'utilisation avancés

### Barre de défilement masquable
```javascript
// Masquer la barre après 2 secondes d'inactivité
let timeout;
document.querySelector('#mon-element').addEventListener('scroll', function() {
    clearTimeout(timeout);
    CustomScrollbar.toggle('#mon-element', true);
    
    timeout = setTimeout(function() {
        CustomScrollbar.toggle('#mon-element', false);
    }, 2000);
});
```

### Barres de défilement thématiques
```javascript
// Appliquer différentes barres selon la section
CustomScrollbar.applyTo('.section-primary', { 
  thumbColor: '#007bff', 
  trackColor: '#e7f1ff' 
});

CustomScrollbar.applyTo('.section-danger', { 
  thumbColor: '#dc3545', 
  trackColor: '#f8d7da' 
});
```

### Indicateur de progression
```javascript
document.querySelector('#article').addEventListener('scroll', function(e) {
    const element = e.target;
    const scrollTop = element.scrollTop;
    const scrollHeight = element.scrollHeight - element.clientHeight;
    const scrollPercentage = (scrollTop / scrollHeight) * 100;
    
    // Mettre à jour un indicateur de progression
    document.querySelector('#progress').style.width = scrollPercentage + '%';
});
```

## Support et assistance

Pour toute question ou assistance technique, contactez notre équipe de support premium via:
- Email: support@customscrollbar.com
- Forum: community.bubble.io/custom-scrollbar

## Mises à jour à venir

- Gestionnaire de préréglages pour sauvegarder différentes configurations
- Support pour les effets parallax liés au défilement
- Interactions tactiles avancées pour mobiles
- Nouvelles animations et transitions

---

&copy; 2025 Custom Scrollbar Premium | Tous droits réservés