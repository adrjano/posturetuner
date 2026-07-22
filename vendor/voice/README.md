# vendor/voice/

Pliki mp3 dla komunikatów głosowych w module Postawa, uporządkowane w podfolderach
językowych — dzięki temu dodanie kolejnego języka w przyszłości to tylko "nagraj/wygeneruj
te same frazy w innym języku i wrzuć do nowego podfolderu", bez zmian w kodzie.

## Teraz: polski (folder `pl/`)

Wygeneruj na https://ttsmp3.com (darmowe, głos polski) i zapisz w `vendor/voice/pl/`
DOKŁADNIE pod tymi nazwami:

| Plik            | Tekst |
|-----------------|-------|
| shoulders.mp3   | Wyrównaj barki, jeden jest wyżej |
| lean.mp3        | Wyprostuj się, nie przechylaj tułowia |
| head.mp3        | Unieś głowę, nie garb się nad gryfem |
| knee.mp3        | Kolano prosto |
| arms.mp3        | Ułóż ręce w pozycji gry, nie opuszczaj ich |
| neck.mp3        | Popraw wysokość gryfu gitary |
| elbow.mp3       | Oprzyj prawe przedramię na krawędzi pudła |
| wrist.mp3       | Wyprostuj nadgarstek lewej ręki |
| thumb.mp3       | Opuść kciuk poniżej gryfu |
| curlL.mp3       | Zaokrąglij palce lewej dłoni |
| curlR.mp3       | Zaokrąglij palce prawej dłoni |
| pos1.mp3        | Wszystko dobrze, tak trzymaj! |
| pos2.mp3        | Świetna postawa! |
| pos3.mp3        | Bardzo dobrze — kontynuuj tak dalej. |
| calib.mp3       | Zapisano wzorcową postawę |

Po dodaniu plików: `npx cap sync android`, przebuduj APK jak zwykle.

## W przyszłości: kolejne języki (np. `en/`, `de/`...)

1. Przetłumacz tych samych 15 fraz na docelowy język.
2. Wygeneruj mp3 (ten sam ttsmp3.com obsługuje wiele języków) i zapisz w nowym
   podfolderze, np. `vendor/voice/en/`, pod tymi samymi 15 nazwami plików.
3. W `modules/postawa.html` znajdź `const VOICE_READY_LANGS = ['pl'];` i dodaj
   kod języka, np. `['pl', 'en']` — to jedyna zmiana w kodzie.

Dopóki dany język nie zostanie dodany do `VOICE_READY_LANGS`, głos w Postawie
po cichu zostaje przy polskim, nawet jeśli w Ustawieniach wybrano inny język
(żeby nie odtwarzać nieistniejących plików).
