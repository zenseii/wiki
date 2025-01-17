---
lang: ko-KR
layout: wiki
section: twilightmenu
category: customization
title: Unlaunch 배경화면 변경하기
description: Unlaunch 배경화면을 만들고 TWiLight Menu++를 이용하여 설치하는 방법
---

You can find premade Unlaunch backgrounds on the [TWiLight Menu++ skins site](https://skins.ds-homebrew.com/unlaunch/).
{:.alert .alert-info}

Using TWiLight Menu++ you can patch the Unlaunch installer to have a custom background image and text color palette. This needs to be a 256 x 192 GIF, with a few restrictions:
- 1번째 프레임만이 보일 것이며, 배경은 움직이지 말아야 합니다.
- 파일은 15472바이트 이하여야 합니다.
- 31 컬러 이상의 GIF는 글씨가 깨짐을 방지하기 위하여 팔레트를 직접 만들어야 합니다.

### 설치하기
1. GIF 파일을 `sd:/_nds/TWiLightMenu/unlaunch/backgrounds`로 복사해 주세요.
1. [최신 Unlaunch 인스톨러](https://problemkaputt.de/unlaunch.zip)를 다운로드하시고, SD 카드로 `UNLAUNCH.DSI`의 압축을 풀어 주세요.
1. TWiLight Menu++ 설정을 여시고, `Unlaunch 설정`으로 가신 다음에 `배경화면`를 클릭하신 다음에 윈하시는 것을 클릭해 주세요.
1. 설정을 종료하신 다음 `Unlaunch DSi 인스톨러`를 열어 주세요.
   - 자신이 설정한 이미지를 사용할 것입니다. 만약 그렇지 않다면 DSi를 끄셔서 GIF 파일이 위의 조건과 맟는지 다시 한번 확인해 주세요.
1. `Install Now`를 눌러 주세요.

### 31 컬러 이상의 GIF 사용하기
As the GIF's palette is loaded to the same area of VRAM as the text palettes it will overwrite them if the palette gets too large, however this can be worked around by including the text palettes in the GIF's palettes. Using this with different colors would also let you have different text colors, should you want that. These instructions will be for [GIMP](https://gimp.org), but any image editor capable of rearranging the palette of an image will work.
1. GIMP에서 이미지를 여시고 256x192인걸 다시 한 번 확인해 주세요.
1. In the menu bar at the top, select `Image` -> `Mode` -> `Indexed...`
1. Select `Generate optimum palette` and set the maximum colors to anything up to 226 colors
1. Select a dithering pattern from the `Color dithering` dropdown
   - Images without dithering generally compress best, but with it will generally look better, try and see which looks best for the size
1. Click `Convert`
1. In the menu bar at the top, select `File` -> `Export As...`, give it a name with the extension `.gif`, and click `Export`
   - If it gives any warnings, click the accept button
1. In the next popup, disable the `GIF comment` and click `Export`
1. Check the size of the exported file, if it's 15,472 bytes or less, then skip to step 13
1. If your GIF is too large, then using either [gifsicle](http://www.lcdf.org/gifsicle/) or [ezgif.com](https://ezgif.com/optimize) you can try optimizing it
   - These instructions will use ezgif as its simpler, being a website
1. https://ezgif.com/optimize를 여셔서 GIF를 업로드해 주세요.
1. Try different compression levels until you find the best one under 15,472 bytes (15.11 KiB), ideally a bit under as GIMP may increase the size a bit
1. Save the optimized GIF and open it in GIMP
1. In the menu bar at the top, select `Windows` -> `Dockable Dialogs` -> `Colormap`
1. Change your current `Foreground color` to #080808 and add 14 new colors with the `+` button
    - If your image doesn't have at least 133 colors you will need to keep adding colors until the last is index 146
1. Right click a color in the Colormap and select `Rearrange Colormap...`
1. Arrange your new colors so they match the ones outlined in red: (The 2nd and 3rd columns starting on the 4th row)<br> ![맞는 텍스트 색이 들어가 있는 팔레트](/assets/images/custom-unlaunch-bg/unlaunch-palette.png)
1. Use the color picker to make your new colors match those in the above image
1. In the menu bar at the top, select `File` -> `Export As...`, give it a name with the extension `.gif`, and click `Export`
1. In the next popup, make sure `GIF comment` is off and click `Export`
1. 이미지 파일이 15472바이트 이하인걸 확인해 주세요. 만약 사이즈가 커졌다면 더 높은 압축 레벨로 10단계부터 다시 해주세요.
1. 작업이 끝났습니다! 위의 [설치하기](#installing)를 따라서 이미지를 설치해 주세요!
