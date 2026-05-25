# DarkSoul Resource Pack

Resource pack resmi untuk plugin **DarkSoul**. Pack ini memuat custom item model, icon GUI, tombol GUI, dan font glyph selector buatan DarkSoul.

## Isi Pack

- `assets/darksoul/textures/gui/selector_background.png` - canvas background selector.
- `assets/darksoul/font/selector.json` - glyph background dan negative/positive spacing.
- `assets/darksoul/font/title_text.json` - font kecil untuk nameplate selector.
- `assets/darksoul/font/text_line_0.json` sampai `text_line_5.json` - font line untuk description di title inventory.
- `assets/darksoul/textures/item/gui/` - texture tombol selector dan icon GUI DarkSoul.
- `assets/darksoul/models/gui/` - model item tombol selector.
- `assets/minecraft/items/light_gray_stained_glass_pane.json` - mapping custom model data tombol GUI.
- `pack.mcmeta` dan `pack.png` - metadata resource pack.

## File Release

ZIP siap pakai:

```text
DarkSoul-ResourcePack-1.0-BETA.zip
```

SHA-1 release ditulis ulang setiap kali ZIP dibuild.

## Konfigurasi Plugin

Di `plugins/DarkSoul/config.yml`, gunakan URL raw GitHub yang dipin ke commit dan SHA-1 ZIP terbaru:

```yaml
resource-pack:
  item-models-enabled: true
  item-model-source: darksoul
  gui-models-enabled: true
  debug-layout: false
  auto-send:
    enabled: true
    url: "https://raw.githubusercontent.com/KangAdit020/DarkSoul-ResourcePack/<commit>/DarkSoul-ResourcePack-1.0-BETA.zip"
    sha1: "<sha1>"
```

## Catatan GUI

Selector DarkSoul memakai chest inventory 54 slot sebagai hitbox. Visual utama dirender lewat title inventory custom bitmap font, sedangkan tombol previous/next/up/down/confirm memakai custom item model. Confirm memakai satu visual lebar di slot 48 dan hitbox invisible di slot 49 serta 50.

Description utama race/class dirender melalui font line `darksoul:text_line_0` sampai `darksoul:text_line_5`, bukan lore item. Lore hanya dipakai saat `debug-layout=true` untuk membaca slot/action.

## Update Pack

Build ZIP dari root repo resource pack:

```powershell
Compress-Archive -Path pack.mcmeta,pack.png,assets -DestinationPath DarkSoul-ResourcePack-1.0-BETA.zip -Force
Get-FileHash -Algorithm SHA1 .\DarkSoul-ResourcePack-1.0-BETA.zip
```
