# HyprBlackscreen

## Requirements

- [hypridle](https://wiki.hyprland.org/Hypr-Ecosystem/hypridle/)
- [eww](https://elkowar.github.io/eww/)

## Install

Make sure directories exist

```sh
mkdir -p ~/.config/hypr/ && mkdir -p ~/.config/eww/
```

Download [`blackscreen.sh`](blackscreen.sh)
```sh
curl https://raw.githubusercontent.com/Ricky12Awesome/hyprblackscreen/refs/heads/main/blackscreen.sh > ~/.config/hypr/blackscreen.sh
```

Add this to your eww.yuck file
```lisp
(defwindow blackscreen[id]
  :geometry (geometry
    ; Make sure to cover full screen and bars
    :x "-200%"
    :y "-200%"
    :width "200%"
    :height "200%"
  :anchor "center")
  :stacking "overlay"
  :exclusive true
  (button
    :style "background: #000000; color: #000000; border: none;"
    :onclick "eww close ${id}"
  )
)
```

Add this to your hypridle.conf file
```conf
listener {
    # Time in seconds to show the blackscreen
    timeout = 60
    on-timeout = ~/.config/hypr/hyprblackscreen/blackscreen.sh open
    on-resume = ~/.config/hypr/hyprblackscreen/blackscreen.sh close
}
```

make sure you having hypridle running if not already, you can do that here https://wiki.hyprland.org/Hypr-Ecosystem/hypridle/#configuration

## Quick Install (fresh install only)
**WILL OVERWRITE EXISTING FILES**
```sh
curl https://raw.githubusercontent.com/Ricky12Awesome/hyprblackscreen/refs/heads/main/blackscreen.sh > ~/.config/hypr/blackscreen.sh
curl https://raw.githubusercontent.com/Ricky12Awesome/hyprblackscreen/refs/heads/main/eww.yuck > ~/.config/eww/eww.yuck
curl https://raw.githubusercontent.com/Ricky12Awesome/hyprblackscreen/refs/heads/main/hypridle.conf > ~/.config/hypr/hypridle.conf
```