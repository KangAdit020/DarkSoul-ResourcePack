# DarkSoul Resource Pack

Resource pack resmi untuk plugin **DarkSoul**. Pack ini dipakai untuk custom item model, icon GUI, tombol GUI, font glyph, dan overlay origin selector.

## Isi Pack

- `assets/darksoul/models/item/` - model item dan GUI button DarkSoul.
- `assets/darksoul/textures/item/` - texture item custom.
- `assets/darksoul/textures/gui/origin_selector/overlay/` - overlay GUI race/class yang sudah diposisikan pixel-perfect.
- `assets/darksoul/font/origin_selector_overlay.json` - custom font untuk menampilkan overlay selector.
- `assets/minecraft/textures/gui/origin_selector/` - asset visual yang diadaptasi untuk tampilan origin selector.
- `pack.mcmeta` dan `pack.png` - metadata resource pack.

## File Release

ZIP siap pakai:

```text
DarkSoul-ResourcePack-1.0-BETA-with-Origins.zip
```

SHA-1 saat ini:

```text
29dfe51a9861d34c5bb6e39b2e17dea4cd8ef3f5
```

## Konfigurasi Plugin

Di `plugins/DarkSoul/config.yml`, gunakan URL release GitHub dan SHA-1 yang sama dengan ZIP terbaru:

```yaml
resource-pack:
  item-models-enabled: true
  item-model-source: darksoul
  gui-models-enabled: true
  debug-layout: false
  auto-send:
    enabled: true
    url: "https://raw.githubusercontent.com/KangAdit020/DarkSoul-ResourcePack/main/DarkSoul-ResourcePack-1.0-BETA-with-Origins.zip"
    sha1: "29dfe51a9861d34c5bb6e39b2e17dea4cd8ef3f5"
```

Setelah ZIP di repo diganti, restart server supaya player menerima resource pack baru. Jika client masih memakai tampilan lama, hapus cache server resource pack di client Minecraft.

## Catatan GUI

Origin selector DarkSoul memakai satu overlay bitmap per race/class agar layout tidak mudah bergeser saat GUI scale atau ukuran window berubah. Overlay tersebut memuat:

- frame selector
- title bar
- icon race/class
- nama race/class
- indicator dots
- description yang sudah di-wrap

Tombol klik tetap memakai slot inventory vanilla, sedangkan visual frame dan text overlay berasal dari custom font resource pack.

## Update Pack

Build resource pack dari project plugin DarkSoul:

```powershell
powershell -ExecutionPolicy Bypass -File scripts\build-resource-pack.ps1
```

Lalu salin ZIP hasil build ke repo ini dan update SHA-1:

```powershell
Get-FileHash -Algorithm SHA1 .\DarkSoul-ResourcePack-1.0-BETA-with-Origins.zip
```

Pastikan SHA di `config.yml` plugin mengikuti ZIP yang sudah di-upload ke repo ini.
