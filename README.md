# HyprBlackscreen

## Requirements

- [hypridle](https://wiki.hyprland.org/Hypr-Ecosystem/hypridle/)
- [eww](https://elkowar.github.io/eww/)

## Install

Make sure directories exist

```sh
mkdir -p ~/.config/hypr/hyprblackscreen/
```

Download [`blackscreen.sh`](blackscreen.sh) to that directory

```sh
curl https://raw.githubusercontent.com/Ricky12Awesome/hyprblackscreen/refs/heads/main/blackscreen.sh > ~/.config/hypr/hyprblackscreen/blackscreen.sh
```

Download [`eww.yuck`](eww.yuck) to that directory

```sh
curl https://raw.githubusercontent.com/Ricky12Awesome/hyprblackscreen/refs/heads/main/eww.yuck > ~/.config/hypr/hyprblackscreen/eww.yuck
```

Add this to your hypridle.conf

```conf
listener {
    # Time in seconds to show the blackscreen
    timeout = 60
    on-timeout = ~/.config/hypr/hyprblackscreen/blackscreen.sh open
    on-resume = ~/.config/hypr/hyprblackscreen/blackscreen.sh close
}
```
or by doing this
```sh
curl https://raw.githubusercontent.com/Ricky12Awesome/hyprblackscreen/refs/heads/main/hypridle.conf >> ~/.config/hypr/hypridle.conf
```

make sure you having hypridle running if not already, you can do that here https://wiki.hyprland.org/Hypr-Ecosystem/hypridle/#configuration