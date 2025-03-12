# Hyprland_Config

## Modifier la configuration 
```cmd
nano ~/.config/hypr/hyprland.conf
```

## Recharger Hyprland 
```cmd
pkill Hyprland
```

# Liste de mes raccourcis
L'ensemble des raccourcis commande par `SUPER`

- Ouvrir un terminal : `Enter`
- Ouvrir Firefox : `N`
- Fermer une application : `Esc`
- Envoyer une fenêtre sur un autre écran : `Shift + 1` (ou 2) (à condigurer selon le nom de vos écrans : `hyprctl monitors`)
- D : Ouvrir Wofi
- B : Ouvrir Discord
- C : Ouvrir Cursord

# Changer de fond d'écran 

```cmd
sudo pacman -S hyprpaper
nano ~/.config/hypr/hyprland.conf
```
Et ajouter ceci : 
```conf
exec-once = hyprpaper
```

Ensuite, créer un fichier de config pour : 
```cmd
mkdir -p ~/.config/hypr
nano ~/.config/hypr/hyprpaper.conf
```

Puis ajouter cette ligne vers son fond d'écran : 
```conf
preload = /home/wolfyz/Téléchargements/montapier.png
wallpaper = eDP-1, /home/wolfyz/Téléchargements/montapier.png
```

### Bonus : Fond d'écran aléatoire 
```
exec-once = hyprpaper
exec-once = find /home/wolfyz/Téléchargements/Wallpapers/ -type f | shuf -n 1 | xargs -I {} echo "wallpaper = eDP-1, {}" > ~/.config/hypr/hyprpaper.conf
exec-once = find /home/wolfyz/Téléchargements/Wallpapers/ -type f | shuf -n 1 | xargs -I {} echo "wallpaper = HDMI-A-1, {}" >> ~/.config/hypr/hyprpaper.conf
```