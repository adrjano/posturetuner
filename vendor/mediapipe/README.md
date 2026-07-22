# vendor/mediapipe/

Ten folder jest celowo pusty w paczce, którą dostałeś — środowisko, w którym
przygotowałem tę aplikację, nie ma dostępu do internetu, więc nie mogłem pobrać
plików binarnych (biblioteka + modele to razem kilkanaście–20+ MB).

## Jak uzupełnić

Z katalogu `gitara-app/` (na maszynie z dostępem do internetu i node/npm):

```bash
bash scripts/fetch-mediapipe-assets.sh
```

Skrypt pobierze i ułoży pliki dokładnie tak, jak oczekuje tego zaktualizowany
`modules/postawa.html`:

```
vendor/mediapipe/
├── vision_bundle.mjs
├── wasm/
│   └── ... (pliki .wasm + .js runtime)
└── models/
    ├── pose_landmarker_lite.task
    └── hand_landmarker.task
```

Po tym kroku `postawa.html` nie łączy się już z żadnym zewnętrznym CDN — cała
funkcjonalność (wykrywanie postawy) działa bez internetu, w tym w finalnym APK.
